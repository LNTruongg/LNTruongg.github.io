---
title: "Security groups and IAM"
date: 2026-11-27
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---

#### Security groups

1. Open VPC Console → **Security groups → Create security group**. Enter the name and description, then select `CoupleLifeAI-vpc`. Create the ALB, EC2 and RDS groups in that order using the table below. Under **Inbound rules → Add rule**, choose the protocol, port and source. When the source is a security group, search for the group you just created. Keep default outbound rules for the lab.

| Name | Inbound | Source |
|---|---|---|
| CoupleLifeAI-SG-ALB | HTTP 80 | Initially closed; restrict CloudFront origin access during ALB setup |
| CoupleLifeAI-SG-EC2 | TCP 8080 | CoupleLifeAI-SG-ALB |
| CoupleLifeAI-SG-RDS | TCP 5432 | CoupleLifeAI-SG-EC2 |

![EC2 inbound rule from ALB](./image_5.3.2/07.02-sg-ec2-configuration.png)
![RDS inbound rule from EC2](./image_5.3.2/08-sg-rds-configuration.png)

Do not expose SSH 22, AI port 8000 or PostgreSQL 5432 to the Internet. App outbound access is needed for ECR, Secrets Manager and external APIs. Restrict ALB inbound access as described in section 5.4.3.

#### EC2 IAM role

1. Open [IAM Roles](https://console.aws.amazon.com/iam/home#/roles), then choose **Create role → AWS service → EC2**.
2. Attach `AmazonSSMManagedInstanceCore` and `AmazonEC2ContainerRegistryReadOnly`. Name the role `CoupleLifeAI-EC2-Role`.

![Initial managed policies](./image_5.3.2/09.02-ec2-iam-role.png)
3. Once the secrets exist, grant `secretsmanager:GetSecretValue` on the two application secret ARNs. The following is a policy example; replace `ACCOUNT_ID` with your account number. Do not grant access to every secret in the account.

```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": "secretsmanager:GetSecretValue",
    "Resource": [
      "arn:aws:secretsmanager:ap-southeast-1:ACCOUNT_ID:secret:couplelife/production/backend-*",
      "arn:aws:secretsmanager:ap-southeast-1:ACCOUNT_ID:secret:couplelife/production/ai-service-*"
    ]
  }]
}
```

In IAM → Roles, open `CoupleLifeAI-EC2-Role`, choose Add permissions → Create inline policy → JSON. Paste the policy, replace `ACCOUNT_ID` with the value from section 5.2, choose Next and Create policy. After creating RDS, open RDS → Databases → `couplelife-db` → Configuration to find the master secret ARN; grant `secretsmanager:GetSecretValue` only on that ARN in a separate bootstrap policy.

Name the inline policy `CoupleLifeSecretsRuntimePolicy`. Create a temporary `CoupleLifeBootstrapRDSPolicy` granting read access only to the RDS master secret for initialization. Remove it after migration and seeding; runtime uses a separate database user.

![IAM permissions during bootstrap](./image_5.3.2/13-ec2-iam-permissions-final.png)

#### Secrets Manager

After creating RDS in section 5.3.3, open **Secrets Manager → Store a new secret → Other type of secret**. Create two application secrets and keep the RDS-managed secret unchanged.

| Secret name | Required keys |
|---|---|
| couplelife/production/ai-service | INTERNAL_API_SECRET, CLOUDFLARE_ACCOUNT_ID, CLOUDFLARE_API_TOKEN, GROQ_API_KEY; ROUTING_PROVIDER_URL if needed |
| couplelife/production/backend | SECRET_KEY, INTERNAL_TOKEN, DATABASE_URL, CORS_ORIGINS |

`INTERNAL_TOKEN` and `INTERNAL_API_SECRET` must match and be strong random ASCII strings; `SECRET_KEY` is a separate value. `DATABASE_URL` uses the application database user `couplelife_app`, database `couplelife_db` and the RDS endpoint. URL-encode special characters in passwords properly. Never use the master password at runtime. With same-origin HTTPS `/api/*`, the browser need not call the ALB domain directly.

In RDS → Databases → `couplelife-db` → Connectivity & security, copy the Endpoint. Create a separate password for `couplelife_app` and use the same password when initializing the DB. Example `DATABASE_URL` format: `postgresql+psycopg2://couplelife_app:PASSWORD@RDS_ENDPOINT:5432/couplelife_db?sslmode=require` (replace PASSWORD with the URL-encoded password and substitute the endpoint). Generate random tokens in a private terminal using `python -c "import secrets; print(secrets.token_hex(32))"`; use separate values for the internal token and SECRET_KEY. Set CORS_ORIGINS in the format required by the backend source; update the CloudFront HTTPS domain in section 5.4.4 if required. Do not use a wildcard with credentials.

Select `aws/secretsmanager`, tag Project = CoupleLifeAI, and do not replicate into another region. Create the secrets and check the list without exposing their values.

![Two application secrets and the RDS-managed secret](./image_5.3.2/12-secrets-manager-created.png)

**Note:** Enter real values for each key, not descriptions or placeholders. See section 5.5.1 if AI Service returns HTTP 500.
