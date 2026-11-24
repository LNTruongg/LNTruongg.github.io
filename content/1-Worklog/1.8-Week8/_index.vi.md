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
- Hiểu cách CloudFront sử dụng CDN và Cache để phân phối nội dung website.
- Tìm hiểu cách Route 53, CloudFront và S3 kết hợp với nhau.
- Tiếp tục phát triển giao diện và các chức năng cơ bản của LoveSpot.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu DNS, Route 53 và các bản ghi A, CNAME, MX. | 02/11/2026 | 02/11/2026 | [Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html) |
| 3 | Tìm hiểu Public Hosted Zone, Private Hosted Zone và TTL. | 03/11/2026 | 03/11/2026 | [Route 53 Hosted Zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-working-with.html) |
| 4 | Tìm hiểu Simple, Weighted, Failover Routing và Health Check. Chỉ đọc tài liệu, không tạo tài nguyên. | 04/11/2026 | 04/11/2026 | [Route 53 Routing Policies](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html) |
| 5 | Tìm hiểu CDN, CloudFront, Origin, Edge Location và cách lưu Cache nội dung. | 05/11/2026 | 05/11/2026 | [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 6 | Tìm hiểu Cache Hit, Cache Miss và cách CloudFront lấy file từ S3. **Làm dự án:** Tiếp tục chỉnh sửa bố cục giao diện LoveSpot bằng React/Vite. | 06/11/2026 | 06/11/2026 | [How CloudFront Works](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowCloudFrontWorks.html) |
| 7 | Ôn tập Route 53, CloudFront và S3. Đọc bảng giá, không tạo tài nguyên AWS. **Làm dự án:** Xem lại cách hiển thị danh sách địa điểm và thông tin đầu vào cho chức năng gợi ý. | 07/11/2026 | 07/11/2026 | [Route 53 Pricing](https://aws.amazon.com/route53/pricing/), [CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/) |

### Kết quả đạt được tuần 8:

**Kiến thức đã tìm hiểu:**

- Hiểu DNS giúp phân giải tên miền và Route 53 dùng để quản lý các bản ghi DNS.
- Phân biệt A Record, CNAME và MX; hiểu Hosted Zone và TTL.
- Biết CloudFront là CDN giúp phân phối nội dung từ các Edge Location.
- Hiểu sự khác nhau giữa Cache Hit và Cache Miss.
- Biết Route 53 xử lý DNS, CloudFront phân phối nội dung và S3 có thể lưu trữ file gốc.

**Tìm hiểu và luyện tập theo tài liệu:**

- Xem ví dụ cấu hình DNS Record và các chính sách định tuyến.
- Tìm hiểu mô hình website tĩnh sử dụng S3 kết hợp CloudFront.
- Đọc bảng giá và không tạo Hosted Zone, Health Check hay CloudFront Distribution để tránh phát sinh chi phí.

**Hoạt động dự án LoveSpot:**

- Tiếp tục xem xét và điều chỉnh bố cục giao diện LoveSpot, tập trung vào phần nhập thông tin và tìm kiếm địa điểm.
- Tìm hiểu cách hiển thị danh sách quán ăn và dữ liệu gợi ý để người dùng dễ xem và lựa chọn.
- Kiểm tra lại luồng thao tác trên giao diện, chuẩn bị cho việc kết nối với Backend và hệ thống gợi ý ở các tuần tiếp theo.

**Khó khăn gặp phải và cách giải quyết:**

- Có nhiều loại DNS Record nên ban đầu khó nhớ. Tôi đọc lại các ví dụ để phân biệt A, CNAME và MX.
- Khi học CloudFront, tôi chưa hiểu vì sao website đã cập nhật nhưng người dùng vẫn thấy nội dung cũ. Sau khi tìm hiểu Cache và TTL, tôi hiểu rõ hơn nguyên nhân.