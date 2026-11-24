---
title: "Worklog Tuần 11"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

- Tìm hiểu AWS Elastic Beanstalk và cách triển khai ứng dụng web.
- Làm quen với Docker, Amazon ECR và Amazon ECS.
- Hiểu các thành phần cơ bản của ECS và chi phí sử dụng.
- Làm dự án LoveSpot: rà soát bản triển khai AWS, sơ đồ kiến trúc và video demo.
- Kiểm tra chức năng gợi ý địa điểm, tạo lịch trình và kết nối giữa các thành phần.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Elastic Beanstalk, Application, Environment, Platform và chi phí các tài nguyên được sử dụng. | 23/11/2026 | 23/11/2026 | [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html), [Elastic Beanstalk Concepts](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html) |
| 3 | Tìm hiểu Docker Image, Container, Amazon ECR và ECS. Đọc về Cluster, Task Definition, Service và Fargate; không tạo tài nguyên thử nghiệm. | 24/11/2026 | 24/11/2026 | [Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html), [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) |
| 4 | **Làm dự án:** Rà soát hệ thống LoveSpot đã deploy lên AWS. Đối chiếu sơ đồ kiến trúc draw.io với các dịch vụ thực tế đang sử dụng. | 25/11/2026 | 25/11/2026 | Source code, tài khoản AWS và sơ đồ kiến trúc LoveSpot |
| 5 | **Làm dự án:** Kiểm tra lại video demo đã quay và ghi chú các bước sử dụng ứng dụng để đưa vào tài liệu Workshop. | 26/11/2026 | 26/11/2026 | Video demo và tài liệu dự án |
| 6 | **Làm dự án:** Kiểm thử kết nối giữa Frontend, Backend và hệ thống gợi ý trên bản deploy. Kiểm tra kết quả địa điểm và lịch trình. | 27/11/2026 | 27/11/2026 | Source code và các tình huống kiểm thử LoveSpot |
| 7 | **Làm dự án:** Tổng hợp tài liệu triển khai, kiểm tra thông tin giám sát và ước tính chi phí AWS. Ghi lại các lỗi còn cần sửa. | 28/11/2026 | 28/11/2026 | Tài liệu Workshop, [AWS Pricing](https://aws.amazon.com/pricing/), [CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) |

### Kết quả tuần 11:

**Kiến thức AWS:**

- Hiểu Elastic Beanstalk hỗ trợ triển khai ứng dụng nhưng tài nguyên AWS bên dưới vẫn có thể tính phí.
- Phân biệt Docker Image và Container.
- Biết ECR dùng để lưu trữ Image, còn ECS dùng để chạy và quản lý Container.
- Tìm hiểu Cluster, Task Definition, Service và Fargate.

**Hoạt động dự án LoveSpot:**

- Đã triển khai LoveSpot lên AWS và hoàn thành sơ đồ kiến trúc hệ thống.
- Đã quay video demo để giới thiệu cách sử dụng ứng dụng.
- Tiếp tục rà soát luồng dữ liệu giữa Frontend, Backend và hệ thống gợi ý.
- Chuẩn bị hoàn thiện tài liệu Workshop, kiểm thử bản deploy và kiểm tra chi phí.

**Khó khăn và hướng xử lý:**

- Cần kiểm tra kết nối API và cấu hình môi trường để ứng dụng hoạt động ổn định sau khi deploy.
- Sơ đồ kiến trúc phải khớp với các tài nguyên AWS thực tế.
- Cần theo dõi chi phí và kiểm tra các tài nguyên không còn sử dụng.