---
title: "Deploy the application"
date: 2026-11-27
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

Once networking and the database are ready, package the backend and AI service as separate Docker images, upload them to ECR and run both on two EC2 instances. Build the frontend as static assets and upload them to S3.

Follow the sections in order. Create the ASG with EC2 health checks in section 5.4.2, initialize the database, then attach the target group and ALB in section 5.4.3. Enable ELB health checks after the application is ready.

#### Contents

1. [Amazon ECR and Docker](5.4.1-ECR-Docker/)
2. [EC2 and Auto Scaling](5.4.2-EC2-ASG/)
3. [Application Load Balancer](5.4.3-Application-Load-Balancer/)
4. [Amazon S3, CloudFront and WAF](5.4.4-S3-CloudFront-WAF/)
5. [CI/CD with GitHub Actions](5.4.5-GitHub-Actions-CICD/)
