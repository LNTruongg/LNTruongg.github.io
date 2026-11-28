---
title: "Workshop overview"
date: 2026-11-27
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

#### Architecture and scope

The application is divided into a frontend, an application/AI tier and a data tier. The FastAPI backend exposes authentication, place and itinerary APIs on port `8080`. The AI service runs on port `8000` in the `couplelife-net` Docker network; the backend calls it internally rather than exposing it directly.

The application request flow is shown below:

```text
Browser (HTTPS)
    |
CloudFront + WAF
    |-- Default (*) --> Private S3 (OAC) --> React/Vite
    |
    +-- /api/* ------> Public ALB (2 AZs)
                          | TCP 8080 / HTTP
                          +-- EC2 A: Backend + AI service
                          +-- EC2 B: Backend + AI service
                               |-- Multi-AZ PostgreSQL (5432)
                               +-- AZ-local NAT --> Groq / Cloudflare / OSRM
```

The `10.0.0.0/16` VPC contains six subnets across `ap-southeast-1a` and `ap-southeast-1b`. Each AZ has a public subnet, a private application subnet and a private database subnet. Two NAT gateways let the EC2 instances pull images and call external APIs without public IP addresses. A gateway endpoint handles applicable S3 traffic from the application subnets. RDS has no public access.

| Component | Role |
|---|---|
| CloudFront, WAF, S3 | Deliver the UI, route API requests and filter traffic at the edge |
| ALB, ASG, EC2 | Distribute requests to two replicas and maintain instance capacity |
| ECR, Secrets Manager, IAM, SSM | Manage images, secrets, permissions and administrative access |
| RDS PostgreSQL | Application data, including 3,072 places in the test result |
| Groq, Cloudflare Workers AI, OSRM | Itinerary refinement, BGE-M3 embeddings and routing |
| CloudWatch, SNS, CloudTrail Event History | Metrics, notifications and management event lookup |

#### Expected results

+ Two EC2 instances in separate AZs, each running both services, and two healthy ALB targets.
+ Frontend accessible through the default CloudFront domain, without buying a domain or creating Route 53 resources.
+ APIs return real places, routes and recommendations. The Multi-AZ RDS standby is for failover, not a read replica for scaling reads.
+ Cost monitoring and a cleanup plan for the end of the 14-day lab.

Check both targets across separate AZs and run a separate failover test to assess recovery. Viewer HTTPS and origin encryption are independent settings; see section 5.4.4.

#### Service selection and the Well-Architected Framework

EC2 t3.small hosts two containers per instance; ASG maintains two replicas and ALB distributes requests. RDS Multi-AZ reduces database disruption risk if an AZ fails; S3 and CloudFront separate frontend traffic from application servers. AZ-local NAT gateways enable outbound connections, while the S3 Gateway Endpoint reduces applicable NAT traffic. Secrets Manager and IAM reduce credential exposure in source; CloudWatch and AWS Budgets support monitoring and cost control.

| AWS Well-Architected pillar | Application in this lab |
|---|---|
| Operational Excellence | Deployment scripts, CI, alarms and cleanup procedure |
| Security | Private subnets, OAC, WAF, IAM, Secrets Manager; verify origin security as in section 5.4.3 |
| Reliability | Two AZs, ALB health checks, ASG and RDS Multi-AZ; test failover separately |
| Performance Efficiency | CDN for static assets, external inference APIs and designed connection pooling |
| Cost Optimization | 14-day estimate, budget alerts, S3 Gateway Endpoint, no purchased domain |
| Sustainability | Right-sized compute, two containers per host, resource removal when no longer needed |

See the [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) for guidance on evaluating these design choices.
