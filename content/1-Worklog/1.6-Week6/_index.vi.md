
---
title: "Worklog Tuần 6"
date: 2026-10-19
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

- Tìm hiểu Amazon RDS và cách AWS hỗ trợ quản lý cơ sở dữ liệu quan hệ.
- Hiểu sự khác nhau giữa Single-AZ, Multi-AZ DB Instance và Read Replica của Amazon RDS.
- Làm quen với Amazon Aurora và mô hình cơ bản gồm Writer, Reader và Cluster Storage.
- Phân biệt cơ sở dữ liệu SQL và NoSQL, tìm hiểu các khái niệm cơ bản của Amazon DynamoDB.
- Làm quen với Partition Key, Sort Key, Query, Scan và tìm hiểu chi phí trước khi quyết định thực hành.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Amazon RDS, khái niệm DB Instance và một số Database Engine phổ biến như MySQL, PostgreSQL. Ôn lại mối liên hệ giữa RDS, VPC và Security Group; đọc tổng quan các yếu tố ảnh hưởng đến chi phí. | 19/10/2026 | 19/10/2026 | [Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html), [RDS Pricing](https://aws.amazon.com/rds/pricing/) |
| 3 | Tìm hiểu các mô hình Single-AZ và Multi-AZ DB Instance của RDS. Phân biệt Standby phục vụ Failover với Read Replica phục vụ nhu cầu đọc dữ liệu; phân tích sơ đồ thay vì tạo nhiều DB Instance. | 20/10/2026 | 20/10/2026 | [RDS Multi-AZ](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html), [RDS Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html) |
| 4 | Tìm hiểu Amazon Aurora, hai phiên bản tương thích MySQL và PostgreSQL. Xem mô hình Aurora Cluster gồm Writer, Reader và tầng lưu trữ dùng chung; tìm hiểu khái niệm Aurora Serverless và chi phí. | 21/10/2026 | 21/10/2026 | [Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html), [Aurora Pricing](https://aws.amazon.com/rds/aurora/pricing/) |
| 5 | Ôn lại kiến thức Database cơ bản và so sánh SQL với NoSQL. Tìm hiểu Amazon DynamoDB, mô hình Key-Value/Document và các thành phần Table, Item, Attribute thông qua dữ liệu ví dụ. | 22/10/2026 | 22/10/2026 | [What Is DynamoDB?](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html), [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| 6 | Tìm hiểu Primary Key trong DynamoDB, gồm Partition Key và Sort Key. Luyện tập thiết kế trên giấy một bảng `Orders` đơn giản với `userId` và `orderId`, không tạo Table thực tế trên AWS. | 23/10/2026 | 23/10/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| 7 | Tìm hiểu sự khác nhau giữa Query và Scan trong DynamoDB. Đọc khái niệm On-Demand và Provisioned Capacity, kiểm tra điều kiện Free Tier; ôn tập bằng bảng so sánh RDS, Aurora và DynamoDB mà không triển khai Database tính phí. | 24/10/2026 | 24/10/2026 | [DynamoDB Query](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html), [DynamoDB Scan](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Scan.html), [DynamoDB Pricing](https://aws.amazon.com/dynamodb/pricing/) |

### Kết quả đạt được tuần 6:

**Kiến thức đã tìm hiểu:**

- Hiểu Amazon RDS là dịch vụ giúp triển khai và quản lý cơ sở dữ liệu quan hệ, hỗ trợ các Database Engine quen thuộc như MySQL và PostgreSQL.
- Biết RDS DB Instance là một đơn vị chạy Database và thường được đặt trong VPC để quản lý kết nối mạng; liên hệ được với kiến thức VPC và Security Group đã học ở tuần 4.
- Phân biệt Single-AZ với mô hình Multi-AZ DB Instance có một Standby ở Availability Zone khác. Hiểu Standby trong mô hình này phục vụ khả năng dự phòng và tự động Failover, không dùng để xử lý truy vấn đọc thông thường.
- Hiểu Read Replica giúp phân chia khối lượng truy vấn đọc khỏi Database chính; phân biệt mục đích Read Scaling với High Availability.
- Biết Amazon Aurora là Database Engine tương thích MySQL/PostgreSQL, có mô hình Cluster với Writer, Reader và tầng lưu trữ dùng chung.
- Hiểu DynamoDB là dịch vụ NoSQL được AWS quản lý hoàn toàn; làm quen với Table, Item, Attribute và sự khác nhau giữa Primary Key chỉ có Partition Key và Primary Key kết hợp Partition Key với Sort Key.
- Biết Query truy xuất dữ liệu dựa trên giá trị Partition Key, còn Scan duyệt các Item trong bảng hoặc Index; hiểu rằng hai cách truy xuất có đặc điểm sử dụng tài nguyên khác nhau.

**Tìm hiểu và luyện tập theo tài liệu:**

- Phân tích các sơ đồ Single-AZ, Multi-AZ DB Instance và Read Replica để so sánh mục đích sử dụng của từng mô hình.
- Xem mô hình Aurora Cluster và xác định vai trò của Writer, Reader và Cluster Storage, thay vì tạo một Cluster có thể phát sinh chi phí.
- Luyện tập mô phỏng bảng `Orders` bằng dữ liệu mẫu trên giấy hoặc trong file ghi chú, với `userId` là Partition Key và `orderId` là Sort Key; không tạo DynamoDB Table trên tài khoản AWS.
- Lập bảng so sánh đơn giản giữa RDS, Aurora và DynamoDB theo loại cơ sở dữ liệu, cách tổ chức dữ liệu và trường hợp sử dụng phù hợp.
- Đọc chính sách chi phí của RDS, Aurora và DynamoDB. Nhận biết DynamoDB có mức sử dụng miễn phí nhất định với Provisioned Capacity nhưng vẫn phải kiểm tra giới hạn và các tính năng có tính phí trước khi thao tác trên tài khoản.

**Khó khăn gặp phải và cách giải quyết:**

- Ban đầu chưa phân biệt rõ Multi-AZ Standby với Read Replica vì cả hai đều liên quan đến việc sao chép dữ liệu. Sau khi đối chiếu sơ đồ và mục đích sử dụng, đã hiểu Standby trong mô hình Multi-AZ DB Instance dùng để Failover, còn Read Replica chủ yếu giúp mở rộng khả năng đọc.
- Chưa quen cách tổ chức dữ liệu trong DynamoDB vì trước đó chủ yếu biết đến bảng SQL. Việc tự đặt ví dụ bảng `Orders` và xác định Partition Key, Sort Key giúp hình dung rõ hơn cách DynamoDB định danh và truy vấn các Item.
