---
title: "Dự toán và tối ưu chi phí"
date: 2026-11-27
weight: 3
chapter: false
pre: " <b> 5.5.3. </b> "
---

Lập dự toán trước khi tạo tài nguyên bằng Pricing Calculator (mục 5.2.1), sau đó theo dõi chi phí trong Billing. Kịch bản thực hành sử dụng tối đa 200 USD AWS Promotional Credits, với ngân sách nội bộ 120 USD cho 14 ngày.

#### 1. Giả định dùng để lập dự toán

- Singapore (`ap-southeast-1`), 2 EC2 On-Demand và 2 NAT hoạt động liên tục; quy ước 730 giờ/tháng, 336 giờ/14 ngày.
- 2 EC2 `t3.small`, mỗi máy 20 GiB gp3; RDS PostgreSQL `db.t3.micro` Multi-AZ, 20 GiB gp3, backup tự động 1 ngày.
- Giả định 10 GB qua NAT mỗi tháng (5 GB/NAT); ít nhất 4 public IPv4 cho NAT và ALB, không phải cho EC2 private. ALB giả định trung bình 1 LCU; không phải kết quả đo tải.
- CloudFront dự kiến 10 GB outbound và 100.000 HTTPS requests/tháng; WAF dự trù tối đa 1 triệu requests như biên an toàn riêng, không phải lưu lượng đồng nhất đã đo. S3 1 GB, 1.000 PUT, 10.000 GET; ECR dự trù 1 GB (hai image ví dụ khoảng 375 MB); 3 secrets và 100.000 API calls/tháng.
- Đây là các đầu vào ước lượng, không phải kết quả load test. Cần theo dõi usage thực tế, bao gồm LCU, NAT, requests, logs, inter-AZ transfer và CPU credits của máy burstable.

#### 2. Kết quả Pricing Calculator

Mở Pricing Calculator, kiểm tra từng cấu hình tính phí (không chỉ phần Description). Ví dụ dự toán dưới đây hiển thị 10 dòng dịch vụ, upfront 0 USD và monthly 223,77 USD.

![Bảng dịch vụ và đơn giá hiển thị](./image_5.5.3/01-aws-pricing-calculator-services.png)

| Dịch vụ | Cấu hình dự toán | USD/tháng |
|---|---|---:|
| VPC | 2 NAT, 10 GB tổng, 4 public IPv4 | 101,32 |
| RDS PostgreSQL | db.t3.micro Multi-AZ, 20 GiB gp3 | 46,40 |
| EC2 và EBS | 2 t3.small, tổng 40 GiB gp3 | 42,38 |
| ALB | 1 ALB, giả định 1 LCU trung bình | 24,24 |
| WAF | 1 Web ACL, 2 rules, 1 triệu requests | 7,60 |
| Secrets Manager | 3 secrets, 100.000 API calls | 1,70 |
| ECR | 1 GB private image storage | 0,10 |
| S3 | 1 GB, PUT/GET theo giả định | 0,03 |
| SNS | Email alerts trong hạn mức giả định | 0,00 |
| CloudFront | Pay-as-you-go, trong hạn mức giả định | 0,00 |
| **Tổng hiển thị** | Trước credits và thuế | **223,77** |

CloudWatch (2 alarms, 1 GB logs dự trù) và CloudTrail (chỉ Event History) được giải trình ngoài 10 dòng Calculator, dự kiến 0 USD nếu thỏa điều kiện miễn phí. CloudWatch log ingestion/retention, snapshot vượt hạn mức, transfer, CPU surplus và các usage phụ có thể làm tăng chi phí. ASG, Launch Template, VPC/subnet, route table, SG, IAM/OIDC, IGW, S3 Gateway Endpoint và Session Manager cho EC2 thông thường không có dòng phí riêng trong cấu hình lab; tài nguyên/lưu lượng liên quan vẫn có thể tính phí. AWS Budgets dùng cho giám sát; kiểm tra phí nếu thêm tính năng nâng cao.

Để kiểm tra dự toán VPC, nhân đơn giá NAT theo giờ với số gateway và thời gian sử dụng, cộng lượng data processing và phí public IPv4. Nhập 5 GB cho mỗi NAT nếu tổng lưu lượng dự kiến là 10 GB. Không tính trùng IPv4 giữa VPC và ALB.

CloudFront sử dụng Pay-as-you-go, không phải flat-rate Free Plan. Theo [CloudFront FAQ](https://aws.amazon.com/cloudfront/faqs/), kiểm tra hạn mức miễn phí cấp tài khoản trước khi sử dụng. WAF tính riêng. Nhập workload giả định 10 GB outbound và 100.000 HTTPS requests/tháng vào Calculator.

Mở [AWS Pricing Calculator](https://calculator.aws/) để tạo dự toán với thông số trên và lưu Share Link. Kiểm tra tổng chi phí sau mỗi lần điều chỉnh workload.

[Dự toán tham khảo CoupleLife AI](https://calculator.aws/#/estimate?id=01ec0aee30504f4a008d08d0db765ffb13d06485). Dùng các thông số trên để tạo dự toán riêng và kiểm tra mức giá hiện hành.

#### 3. Ngân sách 14 ngày và theo dõi Credits

223,77 × 336 / 730 ≈ **103,00 USD**. Đây là quy đổi tuyến tính để lập kế hoạch, không phải invoice; request/storage/Free Tier, thuế, thời gian tạo và xóa tài nguyên có thể làm kết quả thay đổi. So với ngân sách 120 USD, còn 17 USD dự phòng theo mô hình. Dự toán chạy cả tháng vượt 200 USD, nên không để tài nguyên chạy vô thời hạn.

Mở Billing → Credits, xem Total available credit, estimated amount remaining và estimated amount used. Ví dụ bên dưới minh họa số dư 178,04 USD. Đây là số toàn tài khoản; dùng số dư hiện tại của bạn để lập kế hoạch.

![Số dư Credits tại thời điểm chụp](./image_5.5.3/03-aws-credits-balance.png)

Ví dụ với số dư 178,04 USD, nếu dự phòng thêm toàn bộ 103 USD cho 14 ngày thì còn 75,04 USD. Khi hệ thống đã hoạt động, chỉ trừ chi phí dự kiến còn lại từ số dư hiện tại để tránh tính trùng. Tính cả mức sử dụng ngoài dự án nếu dùng chung tài khoản.

1. Mở Billing → Cost Explorer, chọn toàn bộ khoảng sử dụng, Group by Service và lọc theo cost allocation tag nếu đã kích hoạt. So sánh gross usage trước credits, net charges sau credits và Bills.
2. Trong Credits, xem số dư, thời hạn và các dịch vụ đủ điều kiện khấu trừ. Chi phí thực tế phụ thuộc vào mức sử dụng và điều kiện của tài khoản.
3. Dùng AWS Budget 120 USD với ngưỡng 50%, 80%, 100% (mục 5.2.2). Nếu thời gian sử dụng đi qua hai tháng, theo dõi cả chi phí cộng dồn. Budget có độ trễ và không phải giới hạn chi tiêu cứng.
4. Đặt thời hạn sử dụng trước khi triển khai. Theo dõi mỗi ngày; khi số dư còn 100 USD, xem lại dự báo; ở 70 USD, chuẩn bị cleanup; ở 50 USD hoặc khi dự báo vượt ngân sách, dừng workload không cần thiết và tiến hành dọn dẹp theo mục 5.6 sau khi bảo toàn dữ liệu.

#### 4. Tối ưu chi phí trong kiến trúc hiện tại

- Dùng S3 Gateway Endpoint để lưu lượng S3 thích hợp không đi qua NAT; ECR image layers có thể tận dụng endpoint này nhưng API/registry traffic vẫn cần đường truy cập. Hai NAT và Multi-AZ giữ nguyên để đáp ứng thiết kế HA; không hạ cấp chỉ vì muốn giảm số dự toán.
- Cache frontend tại CloudFront, không cache API cá nhân. Dùng hai container trên cùng mỗi EC2 và API embedding/LLM bên ngoài để tránh máy inference lớn. Giữ tag image theo commit; kiểm tra ECR lifecycle, retention log và dọn image cũ khi cần thiết.
- S3 lifecycle có ích cho dữ liệu lâu dài; thực hành 14 ngày ưu tiên dọn tài nguyên đúng hạn. Không mua domain, RI, Savings Plans hoặc Marketplace. Groq, Cloudflare Workers AI, OSRM, GitHub Actions là dịch vụ ngoài AWS: chỉ dùng quota miễn phí đã xác minh, không bật paid fallback; OSRM demo không có SLA. Theo dõi quota trong dashboard của từng dịch vụ.
- Nếu làm môi trường dev riêng sau này, có thể cân nhắc Single-AZ, một NAT hoặc serverless theo workload, nhưng không phải cấu hình HA đang triển khai; đánh giá yêu cầu về tính sẵn sàng trước khi thay đổi kiến trúc.

**Kết quả dự toán:** Khoảng 103 USD cho 14 ngày theo workload giả định, thấp hơn ngân sách 120 USD và hạn mức 200 USD. Đối chiếu Bills và Credits để xác định chi phí thực tế.
