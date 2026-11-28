---
title: "Workshop"
date: 2026-11-27
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Triển khai CoupleLife AI trên AWS

#### Tổng quan

Khi lên kế hoạch hẹn hò ở TP.HCM, người dùng thường phải mở nhiều ứng dụng để tìm quán ăn, xem bản đồ và ước lượng thời gian di chuyển. CoupleLife AI gom các thao tác này vào một website: chọn điểm xuất phát, điểm đến, ngân sách và sở thích; hệ thống tìm địa điểm dọc tuyến và hỗ trợ sắp xếp lịch trình.

Trong workshop này, chúng ta triển khai phiên bản React/Vite và hai dịch vụ FastAPI lên AWS tại Singapore. Frontend nằm trên S3, phân phối qua CloudFront. Hai EC2 trong Auto Scaling Group chạy Backend và AI Service, cùng kết nối một cơ sở dữ liệu PostgreSQL Multi-AZ. Mục tiêu là có một môi trường thực hành chạy được trên Internet mà không cần giữ máy cá nhân hoạt động.

Các bước kết hợp AWS Management Console, AWS CLI và Systems Manager. Thực hiện lần lượt từ chuẩn bị mạng và cơ sở dữ liệu đến triển khai container, phân phối frontend, kiểm thử và dọn dẹp tài nguyên.

#### Nội dung

1. [Tổng quan về Workshop](5.1-Workshop-overview/)
2. [Chuẩn bị](5.2-Prerequisite/)
3. [Thiết lập cơ sở hạ tầng AWS](5.3-Infrastructure/)
4. [Triển khai ứng dụng](5.4-Deployment/)
5. [Kiểm thử, giám sát và chi phí](5.5-Testing-Monitoring-Cost/)
6. [Dọn dẹp tài nguyên](5.6-Cleanup/)
