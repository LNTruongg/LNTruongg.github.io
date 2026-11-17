
---
title: "Worklog Tuần 4"
date: 2026-10-05
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

- Tìm hiểu Amazon VPC và các thành phần mạng cơ bản trong AWS.
- Làm quen với CIDR, Subnet và cách phân biệt Public Subnet với Private Subnet.
- Hiểu vai trò của Route Table, Internet Gateway và NAT Gateway.
- Phân biệt Security Group và Network ACL trong việc kiểm soát lưu lượng mạng.
- Tìm hiểu sơ lược VPC Endpoint, VPC Peering và luyện tập thiết kế sơ đồ VPC đơn giản.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Amazon VPC, mối quan hệ giữa VPC, Region và Availability Zone. Làm quen với CIDR và cách chia dải IP thành các Subnet. | 05/10/2026 | 05/10/2026 | [Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html), [VPC IP Addressing](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-ip-addressing.html) |
| 3 | Tìm hiểu Public Subnet, Private Subnet, Route Table và Internet Gateway. Đọc ví dụ về route `0.0.0.0/0` trỏ đến Internet Gateway. | 06/10/2026 | 06/10/2026 | [Subnet Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/subnet-route-tables.html), [Internet Gateway](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| 4 | Tìm hiểu cách NAT Gateway hỗ trợ tài nguyên trong Private Subnet truy cập Internet. Đọc tài liệu về chi phí NAT Gateway và chỉ phân tích sơ đồ, không tạo tài nguyên này. | 07/10/2026 | 07/10/2026 | [NAT Devices](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat.html), [NAT Gateway Pricing](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-pricing.html) |
| 5 | Ôn lại Security Group từ tuần 1, tìm hiểu Network ACL. So sánh phạm vi áp dụng, Allow/Deny Rules và cơ chế Stateful/Stateless. | 08/10/2026 | 08/10/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html), [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) |
| 6 | Tìm hiểu VPC Endpoint và VPC Peering ở mức cơ bản. Phân biệt S3 Gateway Endpoint với Interface Endpoint, đồng thời đọc lưu ý về chi phí và truyền dữ liệu giữa các VPC. | 09/10/2026 | 09/10/2026 | [S3 Gateway Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html), [VPC Peering](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-peering.html) |
| 7 | Ôn tập kiến thức trong tuần và luyện tập phác thảo sơ đồ VPC bằng draw.io với Public Subnet, Private Subnet, Route Table và các thành phần kết nối được minh họa. Không triển khai EC2, NAT Gateway hoặc các tài nguyên có thể phát sinh phí. | 10/10/2026 | 10/10/2026 | [AWS VPC Examples]( https://docs.aws.amazon.com/vpc/latest/userguide/vpc-examples-intro.html) |

### Kết quả đạt được tuần 4:

**Kiến thức đã tìm hiểu:**

- Hiểu Amazon VPC là một mạng ảo được cách ly về mặt logic, cho phép tổ chức tài nguyên và quản lý kết nối mạng trong AWS.
- Biết VPC thuộc một Region, còn mỗi Subnet nằm trong một Availability Zone. Làm quen với cách viết CIDR, ví dụ `10.0.0.0/16` và `10.0.1.0/24`.
- Phân biệt Public Subnet và Private Subnet dựa trên Route Table. Hiểu rằng có đường định tuyến đến Internet Gateway chưa đủ để một EC2 truy cập được từ Internet; còn cần địa chỉ IP công khai và quy tắc bảo mật phù hợp.
- Nắm được vai trò của NAT Gateway trong việc cho phép tài nguyên ở Private Subnet chủ động kết nối ra Internet.
- Biết Security Group là Stateful và chỉ có Allow Rules, trong khi Network ACL là Stateless và hỗ trợ cả Allow/Deny Rules ở cấp Subnet.
- Hiểu mục đích cơ bản của VPC Peering và VPC Endpoint; biết S3 Gateway Endpoint không có phụ phí riêng, còn Interface Endpoint có thể phát sinh chi phí.

**Tìm hiểu và luyện tập theo tài liệu:**

- Đọc ví dụ về cách bố trí Public Subnet, Private Subnet và hướng đi của lưu lượng mạng qua Route Table.
- Luyện tập phác thảo sơ đồ mạng đơn giản bằng draw.io, đánh dấu các thành phần và đường kết nối để dễ hình dung cách chúng hoạt động.
- So sánh Security Group với Network ACL bằng các tình huống truy cập cơ bản, chẳng hạn cho phép SSH hoặc HTTP.
- Tìm hiểu chi phí trước khi thực hành: không tạo NAT Gateway, Interface Endpoint, EC2 hay Public IPv4 trong nội dung tuần này để tránh phát sinh phí ngoài dự kiến.

**Khó khăn gặp phải và cách giải quyết:**

- Ban đầu khó phân biệt Public Subnet và Private Subnet vì cả hai đều thuộc cùng một VPC. Sau khi xem lại Route Table và sơ đồ Internet Gateway, đã hiểu rõ hơn vai trò của đường định tuyến trong việc xác định loại Subnet.
- Dễ nhầm Security Group với Network ACL vì cả hai đều kiểm soát lưu lượng mạng. Việc so sánh Stateful/Stateless và phạm vi áp dụng giúp phân biệt hai cơ chế này rõ ràng hơn.
