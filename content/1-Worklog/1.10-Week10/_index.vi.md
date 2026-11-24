---
title: "Worklog Tuần 10"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

- Tìm hiểu các chức năng cơ bản của Amazon CloudWatch và AWS CloudTrail trong việc giám sát và kiểm tra hoạt động hệ thống.
- Nắm được vai trò tổng quan của một số dịch vụ bảo mật AWS như IAM Identity Center, KMS, Secrets Manager, GuardDuty và WAF.
- Làm dự án: Tiếp tục phát triển ứng dụng gợi ý quán ăn và tạo lịch trình tại TP.HCM.
- Làm dự án: Phân tích yêu cầu người dùng, rà soát dữ liệu địa điểm và xây dựng hướng xử lý gợi ý.
- Làm dự án: Kiểm thử các tình huống sử dụng và xác định những vấn đề cần cải thiện.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Amazon CloudWatch với Metrics, Logs và Alarms. Tìm hiểu AWS CloudTrail và Event history để phân biệt việc giám sát hiệu năng với ghi nhận hoạt động trên tài khoản AWS. | 16/11/2026 | 16/11/2026 | [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html), [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html) |
| 3 | Tìm hiểu tổng quan IAM Identity Center, KMS, Secrets Manager, GuardDuty và AWS WAF. Ôn tập kiến thức bảo mật, tìm hiểu chi phí và xác định những dịch vụ có thể hữu ích khi triển khai ứng dụng lên AWS trong tương lai. | 17/11/2026 | 17/11/2026 | [AWS Security](https://aws.amazon.com/security/), [AWS Pricing](https://aws.amazon.com/pricing/) |
| 4 | **Làm dự án:** Rà soát mục tiêu và yêu cầu của ứng dụng gợi ý quán ăn, tạo lịch trình tại TP.HCM. Xác định các thông tin đầu vào như khu vực, ngân sách, sở thích ăn uống, thời gian và số lượng địa điểm mong muốn. | 18/11/2026 | 18/11/2026 | Tài liệu yêu cầu và source code dự án |
| 5 | **Làm dự án:** Kiểm tra dữ liệu các địa điểm ăn uống tại TP.HCM, chú ý tên quán, địa chỉ, tọa độ GPS và thông tin đánh giá. Tìm hiểu cách làm sạch dữ liệu, loại bỏ thông tin không hợp lệ và chuẩn bị dữ liệu phục vụ hệ thống gợi ý. | 19/11/2026 | 19/11/2026 | Dataset địa điểm và tài liệu xử lý dữ liệu của dự án |
| 6 | **Làm dự án:** Phân tích logic gợi ý quán ăn dựa trên tiêu chí người dùng. Xem xét cách kết hợp mức độ phù hợp, khoảng cách địa lý và thông tin địa điểm để lựa chọn quán, đồng thời xác định hướng sắp xếp các điểm đến thành một lịch trình hợp lý. | 20/11/2026 | 20/11/2026 | Source code dự án, tài liệu thiết kế hệ thống gợi ý |
| 7 | **Làm dự án:** Kiểm thử các tình huống gợi ý lịch trình với nhiều yêu cầu khác nhau, chẳng hạn thay đổi ngân sách, khu vực hoặc sở thích. Rà soát kết quả và ghi nhận những vấn đề cần tiếp tục cải thiện. | 21/11/2026 | 21/11/2026 | Source code, dữ liệu và các tình huống kiểm thử của dự án |

### Kết quả dự kiến tuần 10:

**Kiến thức AWS cần nắm được:**

- Hiểu CloudWatch hỗ trợ theo dõi hệ thống thông qua Metrics, Logs và Alarms.
- Phân biệt CloudWatch dùng để giám sát hệ thống với CloudTrail dùng để ghi nhận các hoạt động liên quan đến tài khoản và tài nguyên AWS.
- Nắm được mục đích cơ bản của IAM Identity Center, KMS, Secrets Manager, GuardDuty và WAF.
- Hiểu tầm quan trọng của việc kiểm soát chi phí khi lựa chọn dịch vụ AWS.

**Kết quả dự kiến đối với dự án:**

- Làm dự án: Xác định rõ các yêu cầu và chức năng chính của ứng dụng gợi ý quán ăn, tạo lịch trình tại TP.HCM.
- Làm dự án: Hiểu cấu trúc và chất lượng dữ liệu địa điểm, đặc biệt là thông tin địa chỉ và tọa độ GPS.
- Làm dự án: Xác định các tiêu chí gợi ý như sở thích, ngân sách, khu vực và khoảng cách.
- Làm dự án: Xây dựng hoặc cải thiện hướng xử lý từ yêu cầu người dùng đến lựa chọn địa điểm và sắp xếp lịch trình.
- Làm dự án: Chuẩn bị các tình huống kiểm thử để đánh giá kết quả gợi ý.

**Những điểm cần chú ý và hướng giải quyết:**

- **Kiến thức AWS:** Tiếp tục học theo tài liệu chính thức và chưa kích hoạt các dịch vụ có khả năng phát sinh chi phí nếu chưa cần thiết.
- **Làm dự án — Chất lượng dữ liệu:** Kiểm tra các địa điểm thiếu thông tin, có tọa độ không chính xác hoặc dữ liệu chưa đồng nhất.
- **Làm dự án — Mức độ phù hợp:** Kết hợp nhiều tiêu chí thay vì chỉ dựa vào đánh giá của quán ăn.
- **Làm dự án — Tính hợp lý của lịch trình:** Cân nhắc thứ tự điểm đến, khoảng cách và thời gian di chuyển.
- **Làm dự án — Phạm vi triển khai:** Ưu tiên phát triển, kiểm thử trên môi trường local trước khi cân nhắc triển khai AWS.
