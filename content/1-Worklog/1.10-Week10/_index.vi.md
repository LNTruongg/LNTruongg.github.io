---
title: "Worklog Tuần 10"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

- Tìm hiểu CloudWatch, CloudTrail và một số dịch vụ bảo mật AWS.
- Biết cách theo dõi hoạt động hệ thống và kiểm soát chi phí.
- Làm dự án LoveSpot: kiểm tra dữ liệu địa điểm và cải thiện hướng xử lý gợi ý.
- Kiểm thử chức năng tạo lịch trình với các yêu cầu khác nhau.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu CloudWatch Metrics, Logs, Alarms và CloudTrail Event History. Phân biệt giám sát hệ thống với ghi nhận hoạt động AWS. | 16/11/2026 | 16/11/2026 | [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html), [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html) |
| 3 | Tìm hiểu IAM Identity Center, KMS, Secrets Manager, GuardDuty và WAF. Đọc bảng giá, không kích hoạt dịch vụ tính phí. | 17/11/2026 | 17/11/2026 | [AWS Security](https://aws.amazon.com/security/), [AWS Pricing](https://aws.amazon.com/pricing/) |
| 4 | **Làm dự án:** Rà soát yêu cầu LoveSpot, gồm khu vực, ngân sách, sở thích ăn uống và thời gian của người dùng. | 18/11/2026 | 18/11/2026 | Tài liệu yêu cầu và source code LoveSpot |
| 5 | **Làm dự án:** Kiểm tra dữ liệu quán ăn tại TP.HCM, chú ý địa chỉ, tọa độ GPS và đánh giá. Xem xét các địa điểm thiếu thông tin. | 19/11/2026 | 19/11/2026 | Dataset và tài liệu xử lý dữ liệu LoveSpot |
| 6 | **Làm dự án:** Xem lại cách xếp hạng quán ăn theo sở thích, ngân sách và khoảng cách. Tìm hiểu cách sắp xếp các địa điểm thành lịch trình hợp lý. | 20/11/2026 | 20/11/2026 | Source code và tài liệu hệ thống gợi ý |
| 7 | **Làm dự án:** Kiểm thử chức năng gợi ý với nhiều mức ngân sách, khu vực và sở thích. Ghi lại các trường hợp cần chỉnh sửa. | 21/11/2026 | 21/11/2026 | Source code và các tình huống kiểm thử LoveSpot |

### Kết quả tuần 10:

**Kiến thức AWS:**

- Hiểu CloudWatch dùng để theo dõi Metrics, Logs và Alarms.
- Biết CloudTrail ghi nhận các hoạt động trên tài khoản và tài nguyên AWS.
- Nắm được mục đích cơ bản của IAM Identity Center, KMS, Secrets Manager, GuardDuty và WAF.
- Tìm hiểu chi phí trước khi sử dụng, chưa kích hoạt thêm dịch vụ AWS.

**Hoạt động dự án LoveSpot:**

- Rà soát các thông tin đầu vào của chức năng gợi ý địa điểm và tạo lịch trình.
- Kiểm tra chất lượng dữ liệu quán ăn, đặc biệt là địa chỉ, GPS và đánh giá.
- Xem lại logic lựa chọn địa điểm theo nhiều tiêu chí thay vì chỉ dựa vào điểm đánh giá.
- Kiểm thử các trường hợp thay đổi ngân sách, khu vực và sở thích để tìm những điểm cần cải thiện.

**Khó khăn và hướng xử lý:**

- Một số địa điểm có thông tin chưa đầy đủ hoặc tọa độ GPS cần kiểm tra lại. Cần lọc dữ liệu không hợp lệ trước khi đưa vào gợi ý.
- Việc chọn quán phù hợp chưa đủ để tạo lịch trình tốt. Cần chú ý thêm khoảng cách và thứ tự các điểm đến.
- Ưu tiên kiểm thử trên local trước khi đưa hệ thống lên AWS.