---
title: "Cost estimation and optimization"
date: 2026-11-27
weight: 3
chapter: false
pre: " <b> 5.5.3. </b> "
---

Estimate costs before creating resources using Pricing Calculator (section 5.2.1), then track usage in Billing. This lab scenario uses up to USD 200 in AWS Promotional Credits, with a USD 120 internal budget for 14 days.

#### 1. Workload assumptions

- Singapore (`ap-southeast-1`), two On-Demand EC2 instances and two NAT gateways running continuously; a standard 730-hour month and a 336-hour demo.
- Two `t3.small` instances, 20 GiB gp3 each; RDS PostgreSQL `db.t3.micro` Multi-AZ, 20 GiB gp3, one-day automated backup.
- 10 GB monthly NAT data in total (5 GB per gateway); at least four public IPv4 addresses for NAT and ALB, not for private EC2. Assume one average ALB LCU, not a measured load result.
- CloudFront: 10 GB outbound and 100,000 HTTPS requests per month; WAF reserves a separate upper scenario of one million requests, not a measured common traffic count. S3: 1 GB, 1,000 PUT and 10,000 GET; ECR: 1 GB allowance (two example images total about 375 MB); three secrets and 100,000 API calls per month.
- These are planning inputs rather than load-test measurements. Monitor actual LCU, NAT, requests, logs, inter-AZ transfer and burstable-instance CPU credits.

#### 2. Pricing Calculator result

Open Pricing Calculator and check each billable configuration field, not just its Description. The example estimate shows ten services, USD 0 upfront and USD 223.77 monthly.

![Displayed services and estimated costs](./image_5.5.3/01-aws-pricing-calculator-services.png)

| Service | Estimated configuration | USD/month |
|---|---|---:|
| VPC | 2 NAT gateways, 10 GB total, 4 public IPv4 addresses | 101.32 |
| RDS PostgreSQL | db.t3.micro Multi-AZ, 20 GiB gp3 | 46.40 |
| EC2 and EBS | 2 t3.small, 40 GiB gp3 total | 42.38 |
| ALB | 1 ALB, assumed average 1 LCU | 24.24 |
| WAF | 1 Web ACL, 2 rules, 1 million requests | 7.60 |
| Secrets Manager | 3 secrets, 100,000 API calls | 1.70 |
| ECR | 1 GB private image storage | 0.10 |
| S3 | 1 GB, assumed PUT/GET workload | 0.03 |
| SNS | Email alerts within assumed allowance | 0.00 |
| CloudFront | Pay-as-you-go, within assumed allowance | 0.00 |
| **Displayed total** | Before credits and tax | **223.77** |

CloudWatch (two alarms and 1 GB estimated logs) and CloudTrail (Event History only) are accounted for separately from the ten Calculator rows, at an assumed USD 0 if free allowances apply. Log ingestion and retention, excess backup storage, transfer, surplus CPU credits and other usage may increase charges. ASG, Launch Template, VPC/subnets, route tables, SGs, IAM/OIDC, IGW, the S3 gateway endpoint and standard Session Manager access to EC2 have no separate fee in this lab configuration; related resources or traffic may incur charges. AWS Budgets is used for monitoring; check pricing before adding advanced features.

To check VPC costs, multiply the hourly NAT rate by the gateway count and duration, then add data processing and public IPv4 fees. Enter 5 GB per NAT gateway for a total of 10 GB. Avoid double-counting public IPv4 charges under VPC and ALB.

CloudFront uses Pay-as-you-go rather than the flat-rate Free Plan. See the [CloudFront FAQ](https://aws.amazon.com/cloudfront/faqs/) for account-wide free allowances. WAF is billed separately. Enter the assumed workload of 10 GB outbound and 100,000 HTTPS requests per month in Calculator.

Open [AWS Pricing Calculator](https://calculator.aws/) to create an estimate with the settings above and save the share link. Check the total after each workload change.

[CoupleLife AI reference estimate](https://calculator.aws/#/estimate?id=01ec0aee30504f4a008d08d0db765ffb13d06485). Use the settings above to create your own estimate and check current rates.

#### 3. Fourteen-day budget and credit tracking

223.77 × 336 / 730 ≈ **USD 103.00**. This is a linear planning conversion, not an invoice. Requests, storage, free allowances, taxes, provisioning and deletion duration can change actual costs. The model leaves USD 17 against the USD 120 budget. A full month would exceed USD 200, so resources must not run indefinitely.

Open Billing → Credits and review Total available credit, estimated amount remaining and estimated amount used. The example below shows USD 178.04 remaining. These are account-wide values; use your current balance for planning.

![Credit balance at the time of capture](./image_5.5.3/03-aws-credits-balance.png)

For example, reserving another USD 103 for 14 days against USD 178.04 leaves USD 75.04. Once the system is running, subtract only the remaining estimated cost from the current credit balance to avoid double-counting. Include unrelated usage if the account is shared.

1. Open Billing → Cost Explorer, select the entire usage period, group by Service and filter by activated cost allocation tags if available. Compare gross usage before credits, net charges after credits and Bills.
2. In Credits, review the balance, expiry and eligible services. Actual charges depend on usage and account conditions.
3. Use the USD 120 AWS Budget with 50%, 80% and 100% thresholds (section 5.2.2). If usage spans two months, also track cumulative costs. Budget notifications may lag and are not a hard spending cap.
4. Set a usage deadline before deployment. Review daily: at USD 100 remaining, revisit the forecast; at USD 70, prepare cleanup; at USD 50 or if the forecast exceeds the budget, stop unnecessary workloads and follow section 5.6 after safeguarding data.

#### 4. Cost optimization in the deployed architecture

- The S3 gateway endpoint keeps applicable S3 traffic off NAT; ECR image layers can benefit, while API/registry traffic still requires connectivity. Retain both NAT gateways and Multi-AZ for the HA design rather than downgrading simply to lower the estimate.
- Cache static assets at CloudFront, not personalized API responses. Co-locate the two containers on each EC2 and use external embedding/LLM APIs rather than a large inference instance. Keep commit-tagged images; review ECR lifecycle, log retention and old-image cleanup as needed.
- S3 lifecycle can help with long-lived data; timely teardown is more important for this 14-day lab. Do not buy a domain, RI, Savings Plans or Marketplace software. Groq, Cloudflare Workers AI, OSRM and GitHub Actions are external services: verify free quotas, disable paid fallback, and note that the public OSRM demo has no SLA. Monitor the quota in each provider dashboard.
- A separate future development environment could use Single-AZ, one NAT or serverless depending on workload, but these are not the deployed HA configuration; evaluate availability requirements before changing the architecture.

**Estimated result:** Approximately USD 103 for 14 days under the assumed workload, below both the USD 120 budget and the USD 200 credit limit. Reconcile Bills and Credits to determine actual cost.
