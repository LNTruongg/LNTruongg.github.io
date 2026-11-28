---
title: "Tổng quan về Workshop"
date: 2026-11-27
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

#### Kiến trúc và phạm vi

Ứng dụng được chia thành frontend, tầng xử lý nghiệp vụ và AI, cùng tầng dữ liệu. Backend FastAPI cung cấp API xác thực, địa điểm và lịch trình trên cổng `8080`. AI Service chạy cổng `8000` trong Docker network `couplelife-net`; chỉ Backend gọi dịch vụ này qua mạng nội bộ container.

Luồng xử lý của ứng dụng:

```text
Browser (HTTPS)
    |
CloudFront + WAF
    |-- Default (*) --> S3 private (OAC) --> React/Vite
    |
    +-- /api/* ------> Public ALB (2 AZ)
                          | TCP 8080 / HTTP
                          +-- EC2 A: Backend + AI Service
                          +-- EC2 B: Backend + AI Service
                               |-- PostgreSQL Multi-AZ (5432)
                               +-- NAT theo AZ --> Groq / Cloudflare / OSRM
```

VPC `10.0.0.0/16` có sáu subnet trên `ap-southeast-1a` và `ap-southeast-1b`. Mỗi AZ có một public subnet, một private app subnet và một private database subnet. Hai NAT Gateway giúp các EC2 không có IP công cộng vẫn tải image và gọi các API bên ngoài. S3 Gateway Endpoint được dùng cho lưu lượng S3 phù hợp từ app subnet. RDS không mở public access.

| Thành phần | Vai trò |
|---|---|
| CloudFront, WAF, S3 | Phân phối giao diện, định tuyến API và lọc request ở lớp biên |
| ALB, ASG, EC2 | Phân phối request đến hai bản sao ứng dụng, duy trì số lượng instance |
| ECR, Secrets Manager, IAM, SSM | Quản lý image, cấu hình bí mật, quyền và truy cập quản trị |
| RDS PostgreSQL | Lưu dữ liệu ứng dụng, 3.072 địa điểm theo kết quả kiểm thử |
| Groq, Cloudflare Workers AI, OSRM | Tinh chỉnh lịch trình, embedding BGE-M3 và tính tuyến đường |
| CloudWatch, SNS, CloudTrail Event History | Theo dõi chỉ số, cảnh báo và tra cứu hoạt động quản trị |

#### Kết quả cần đạt

+ Hai EC2 ở hai AZ, cùng chạy Backend và AI Service; cả hai target của ALB ở trạng thái Healthy.
+ Frontend truy cập được bằng domain mặc định của CloudFront. Không yêu cầu mua domain hay tạo Route 53.
+ API đọc được dữ liệu thật, trả về tuyến đường và gợi ý. RDS Multi-AZ có một standby phục vụ failover, không phải read replica để phân tải truy vấn.
+ Theo dõi chi phí và chuẩn bị dọn dẹp sau 14 ngày.

Kiểm tra cả hai target ở hai AZ và thực hiện bài thử failover riêng để đánh giá khả năng phục hồi. HTTPS tại CloudFront và mã hóa kết nối origin là hai cấu hình độc lập; xem mục 5.4.4.

#### Lựa chọn dịch vụ và Well-Architected Framework

EC2 t3.small chạy hai container trên mỗi máy; ASG duy trì hai bản sao và ALB phân phối request. RDS Multi-AZ giúp giảm rủi ro gián đoạn DB khi một AZ gặp sự cố; S3 và CloudFront tách tải frontend khỏi máy chủ ứng dụng. Hai NAT phục vụ kết nối ra ngoài theo AZ, S3 Gateway Endpoint giảm lưu lượng NAT phù hợp. Secrets Manager và IAM hạn chế lưu thông tin đăng nhập trong source; CloudWatch và AWS Budgets hỗ trợ theo dõi vận hành và chi phí.

| Trụ cột AWS Well-Architected | Áp dụng trong lab |
|---|---|
| Operational Excellence | Script triển khai, CI, alarms và quy trình dọn dẹp |
| Security | Private subnets, OAC, WAF, IAM, Secrets Manager; kiểm tra bảo mật origin theo mục 5.4.3 |
| Reliability | Hai AZ, ALB health checks, ASG và RDS Multi-AZ; kiểm tra failover riêng |
| Performance Efficiency | CDN cho static assets, inference qua API ngoài AWS, connection pooling theo thiết kế |
| Cost Optimization | Dự toán 14 ngày, budget alerts, S3 Gateway Endpoint, không mua domain |
| Sustainability | Chọn máy phù hợp workload, dùng chung host cho hai container và giải phóng tài nguyên khi không còn sử dụng |

Tham khảo [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) để đánh giá các quyết định thiết kế.
