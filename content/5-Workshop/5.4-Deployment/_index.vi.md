---
title: "Triển khai ứng dụng"
date: 2026-11-27
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

Sau khi mạng và database được chuẩn bị, chúng ta đóng gói Backend và AI Service thành hai Docker images, đưa lên ECR rồi chạy trên hai EC2. Frontend build thành static assets và đưa lên S3.

Thực hiện lần lượt các mục dưới đây. Tạo ASG bằng EC2 health checks ở mục 5.4.2, khởi tạo database rồi gắn Target Group và ALB ở mục 5.4.3. Chỉ bật ELB health checks khi ứng dụng đã sẵn sàng.

#### Nội dung

1. [Amazon ECR và Docker](5.4.1-ECR-Docker/)
2. [EC2 và Auto Scaling](5.4.2-EC2-ASG/)
3. [Application Load Balancer](5.4.3-Application-Load-Balancer/)
4. [Amazon S3, CloudFront và WAF](5.4.4-S3-CloudFront-WAF/)
5. [CI/CD với GitHub Actions](5.4.5-GitHub-Actions-CICD/)
