---
title: "Thiết lập cơ sở hạ tầng AWS"
date: 2026-11-27
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

Ở phần này, chúng ta chuẩn bị mạng, quyền truy cập và database trước khi chạy container. Việc tách public subnet, app subnet và database subnet giúp giới hạn đường truy cập thay vì đặt toàn bộ ứng dụng trên Internet.

Thực hiện theo thứ tự VPC → Security Groups/IAM → RDS. Hai application secrets được tạo sau khi có RDS và thông tin cấu hình ứng dụng, vì vậy có thể quay lại mục 5.3.2 để hoàn tất chúng trước khi tạo EC2.

#### Nội dung

1. [VPC và Networking](5.3.1-VPC-Networking/)
2. [Security Groups và IAM](5.3.2-Security-IAM/)
3. [Amazon RDS PostgreSQL](5.3.3-RDS-PostgreSQL/)
