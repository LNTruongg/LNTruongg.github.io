---
title: "Worklog Tuần 11"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

- Tìm hiểu AWS Elastic Beanstalk và cách dịch vụ này hỗ trợ triển khai ứng dụng web.
- Làm quen với Docker, Container và Docker Image.
- Hiểu Amazon ECR dùng để lưu Image, còn Amazon ECS dùng để chạy và quản lý Container.
- Biết các thành phần cơ bản của ECS và chú ý chi phí trước khi thực hành.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Elastic Beanstalk và cách dịch vụ này hỗ trợ đưa ứng dụng web lên AWS mà không cần tự cấu hình mọi thành phần hạ tầng. | 23/11/2026 | 23/11/2026 | [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html) |
| 3 | Tìm hiểu Application, Environment và Platform trong Elastic Beanstalk. Đọc ví dụ cập nhật phiên bản ứng dụng và xem vì sao môi trường chạy vẫn có thể phát sinh phí. | 24/11/2026 | 24/11/2026 | [Elastic Beanstalk Concepts](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html), [Elastic Beanstalk Pricing](https://aws.amazon.com/elasticbeanstalk/pricing/) |
| 4 | Tìm hiểu Docker và Container. Phân biệt Docker Image với Container, đọc ví dụ Dockerfile dùng để đóng gói ứng dụng. | 25/11/2026 | 25/11/2026 | [Containers on Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-configuration.html) |
| 5 | Tìm hiểu Amazon ECR, Repository và Image Tag. Xem cách Image được lưu trên ECR để các dịch vụ khác có thể sử dụng; không tạo Repository thực tế. | 26/11/2026 | 26/11/2026 | [Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html) |
| 6 | Tìm hiểu Amazon ECS và các khái niệm Cluster, Task Definition, Task và Service. Đọc về hai cách chạy Container phổ biến trên EC2 và Fargate, không khởi chạy Task. | 27/11/2026 | 27/11/2026 | [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html), [ECS Task Definitions](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definitions.html) |
| 7 | Ôn tập sự khác nhau giữa Elastic Beanstalk, ECR và ECS. Xem lại quá trình từ Docker Image đến ECR rồi ECS, đồng thời đọc bảng giá để tránh phát sinh chi phí. | 28/11/2026 | 28/11/2026 | [Amazon ECS Pricing](https://aws.amazon.com/ecs/pricing/), [Amazon ECR Pricing](https://aws.amazon.com/ecr/pricing/) |

### Kết quả dự kiến tuần 11:

**Kiến thức cần nắm được:**

- Hiểu Elastic Beanstalk giúp đơn giản hóa việc triển khai và quản lý ứng dụng, nhưng các tài nguyên như EC2 hoặc Load Balancer được tạo ra vẫn có thể tính phí.
- Biết Docker Image là gói chứa ứng dụng và các thành phần cần thiết để chạy; Container là môi trường chạy được tạo từ Image.
- Hiểu ECR dùng để lưu trữ Container Image, còn ECS giúp chạy và quản lý các Container trên AWS.
- Làm quen với Cluster, Task Definition, Task và Service trong ECS; biết ECS có thể sử dụng EC2 hoặc Fargate để chạy ứng dụng.

**Ôn tập và tìm hiểu theo tài liệu:**

- Xem ví dụ triển khai ứng dụng web bằng Elastic Beanstalk và các thành phần AWS được tạo phía sau.
- Đọc ví dụ Dockerfile và quá trình lưu Image trên ECR, sau đó sử dụng Image trong ECS.
- Chỉ tìm hiểu qua tài liệu, không tạo Elastic Beanstalk Environment, ECR Repository hoặc chạy ECS Task để tránh chi phí ngoài dự kiến.

**Những điểm cần chú ý và cách tìm hiểu:**

- Image và Container là hai khái niệm khá gần nhau. Có thể ghi nhớ đơn giản: Image là bản đóng gói ứng dụng, còn Container là phiên bản đang chạy từ Image đó.
- ECR và ECS cũng dễ bị lẫn vai trò. Khi ôn lại quy trình, chỉ cần nhớ ECR lưu Image, còn ECS sử dụng Image để chạy và quản lý Container.