
---
title: "Worklog Tuần 10"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

- Tìm hiểu cách Amazon CloudWatch theo dõi hoạt động của các dịch vụ AWS.
- Làm quen với Metrics, Logs và Alarms.
- Hiểu AWS CloudTrail ghi lại những hoạt động nào trên tài khoản AWS.
- Biết vai trò cơ bản của một số dịch vụ bảo mật như IAM Identity Center, KMS, Secrets Manager, GuardDuty và WAF.
- Ôn tập kiến thức và kiểm tra chi phí trước khi sử dụng dịch vụ.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Amazon CloudWatch và Metrics. Xem ví dụ theo dõi mức sử dụng CPU của EC2 mà không cần tạo máy chủ mới. | 16/11/2026 | 16/11/2026 | [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) |
| 3 | Tìm hiểu CloudWatch Logs và Alarms. Đọc ví dụ cảnh báo khi CPU vượt ngưỡng; không tạo Alarm để tránh phí ngoài dự kiến. | 17/11/2026 | 17/11/2026 | [CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html), [CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Alarms.html) |
| 4 | Tìm hiểu AWS CloudTrail và Event history. Xem cách tra cứu các hoạt động như đăng nhập hoặc thay đổi tài nguyên, rồi so sánh CloudTrail với CloudWatch. | 18/11/2026 | 18/11/2026 | [CloudTrail Event History](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html) |
| 5 | Tìm hiểu IAM Identity Center, AWS KMS và Secrets Manager ở mức cơ bản: quản lý quyền truy cập, khóa mã hóa và thông tin bí mật của ứng dụng. | 19/11/2026 | 19/11/2026 | [IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html), [AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html), [Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/) |
| 6 | Tìm hiểu Amazon GuardDuty và AWS WAF. Xem ví dụ phát hiện hoạt động đáng ngờ và lọc request không mong muốn vào website; không bật các dịch vụ này. | 20/11/2026 | 20/11/2026 | [Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html), [AWS WAF](https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html) |
| 7 | Ôn tập CloudWatch, CloudTrail và các dịch vụ Security đã học. Đọc bảng giá, lưu ý những tính năng có thể phát sinh phí trước khi thực hành. | 21/11/2026 | 21/11/2026 | [CloudWatch Pricing](https://aws.amazon.com/cloudwatch/pricing/), [CloudTrail Pricing](https://aws.amazon.com/cloudtrail/pricing/), [GuardDuty Pricing](https://aws.amazon.com/guardduty/pricing/) |

### Kết quả dự kiến tuần 10:

**Kiến thức cần nắm được:**

- Hiểu CloudWatch giúp theo dõi tình trạng hệ thống qua Metrics, Logs và Alarms.
- Biết Metrics là các số liệu như CPU Usage, Logs ghi lại thông tin hoạt động, còn Alarms dùng để cảnh báo khi vượt ngưỡng.
- Hiểu CloudTrail giúp kiểm tra những hoạt động quản lý đã diễn ra trên tài khoản AWS. Event history cho phép xem miễn phí các management events trong 90 ngày gần nhất.
- Biết IAM Identity Center hỗ trợ quản lý quyền truy cập, KMS quản lý khóa mã hóa và Secrets Manager quản lý thông tin bí mật.
- Hiểu GuardDuty hỗ trợ phát hiện hoạt động đáng ngờ, còn AWS WAF giúp lọc các HTTP/HTTPS request tới ứng dụng web.

**Ôn tập và tìm hiểu theo tài liệu:**

- Xem ví dụ cảnh báo CPU cao và ví dụ tra cứu một hoạt động trong CloudTrail.
- Ôn lại vai trò của CloudWatch và CloudTrail bằng những tình huống đơn giản.
- Chỉ đọc tài liệu, không tạo Alarm, Trail, khóa KMS, Secret hoặc bật GuardDuty/WAF để tránh chi phí không cần thiết.

**Những điểm cần chú ý và cách tìm hiểu:**

- Metrics, Logs và CloudTrail đều có liên quan đến việc theo dõi hệ thống. Có thể ghi nhớ bằng ví dụ: Metrics cho biết CPU đang dùng bao nhiêu, Logs ghi lại lỗi ứng dụng, còn CloudTrail giúp biết ai đã thực hiện thao tác trên AWS.
- Các dịch vụ Security có khá nhiều tên và chức năng. Nên học theo mục đích của từng dịch vụ thay vì cố nhớ hết tính năng, chẳng hạn bảo vệ mật khẩu, quản lý khóa mã hóa hoặc phát hiện nguy cơ.
