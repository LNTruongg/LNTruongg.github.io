
---
title: "Worklog Tuần 8"
date: 2026-11-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

- Tìm hiểu DNS và cách Amazon Route 53 quản lý tên miền.
- Làm quen với các DNS Record, Hosted Zone và TTL.
- Hiểu CDN là gì và Amazon CloudFront giúp website tải nội dung nhanh hơn như thế nào.
- Ôn lại cách Route 53, CloudFront và S3 kết hợp với nhau, đồng thời chú ý chi phí sử dụng.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu DNS và Route 53. Đọc về các bản ghi thường gặp như A, CNAME và MX. | 02/11/2026 | 02/11/2026 | [Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html) |
| 3 | Tìm hiểu Hosted Zone, sự khác nhau giữa Public và Private Hosted Zone, và ý nghĩa của TTL. | 03/11/2026 | 03/11/2026 | [Route 53 Hosted Zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-working-with.html) |
| 4 | Tìm hiểu đơn giản về các cách định tuyến Simple, Weighted, Failover và chức năng Health Check. Chỉ xem tài liệu, không tạo tài nguyên. | 04/11/2026 | 04/11/2026 | [Route 53 Routing Policies](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html) |
| 5 | Tìm hiểu CDN và CloudFront. Làm quen với Origin, Edge Location và cách CloudFront lưu Cache nội dung website. | 05/11/2026 | 05/11/2026 | [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 6 | Tìm hiểu Cache Hit và Cache Miss. Xem ví dụ CloudFront lấy hình ảnh hoặc file tĩnh từ S3 để gửi đến người dùng. | 06/11/2026 | 06/11/2026 | [How CloudFront Works](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowCloudFrontWorks.html) |
| 7 | Ôn tập Route 53 và CloudFront, xem lại cách hai dịch vụ hoạt động cùng S3. Đọc thêm về chi phí, không tạo tên miền hay CloudFront Distribution. | 07/11/2026 | 07/11/2026 | [Route 53 Pricing](https://aws.amazon.com/route53/pricing/), [CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/) |

### Kết quả đạt được tuần 8:

**Kiến thức đã tìm hiểu:**

- Hiểu DNS giúp chuyển tên miền thành thông tin để tìm đến máy chủ; Route 53 giúp quản lý tên miền và các bản ghi DNS.
- Biết A Record trỏ đến địa chỉ IPv4, CNAME trỏ đến tên miền khác và MX dùng cho email.
- Hiểu Hosted Zone là nơi quản lý DNS Record và TTL liên quan đến thời gian lưu Cache của bản ghi.
- Biết CloudFront là dịch vụ CDN, giúp cung cấp nội dung từ các Edge Location để người dùng truy cập nhanh hơn.
- Phân biệt được vai trò cơ bản: Route 53 xử lý DNS, CloudFront phân phối nội dung, còn S3 có thể là nơi lưu file gốc.

**Ôn tập và tìm hiểu theo tài liệu:**

- Xem các ví dụ DNS Record và cách Route 53 điều hướng truy cập website.
- Ôn lại website tĩnh trên S3 đã học ở tuần 3, tìm hiểu thêm cách CloudFront hỗ trợ tải hình ảnh và file tĩnh.
- Đọc bảng giá AWS. Không mua tên miền, tạo Hosted Zone, Health Check hoặc CloudFront Distribution để tránh phát sinh chi phí.

**Khó khăn gặp phải và cách giải quyết:**

- Có khá nhiều loại DNS Record nên việc nhớ chức năng của từng loại mất thời gian. Tôi đọc lại những ví dụ đơn giản để ghi nhớ các loại thường dùng như A, CNAME và MX.
- Khi học CloudFront, tôi thắc mắc vì sao website đã cập nhật mà đôi khi người dùng vẫn thấy nội dung cũ. Tìm hiểu thêm về Cache và TTL giúp tôi hiểu rằng nội dung có thể vẫn đang được lưu tạm trong một khoảng thời gian.
