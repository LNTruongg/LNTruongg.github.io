---
title: "Worklog Tuần 9"
date: 2026-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

- Tìm hiểu các dịch vụ nhắn tin và xử lý sự kiện trên AWS.
- Phân biệt Amazon SQS, SNS và SES.
- Hiểu cách Amazon EventBridge xử lý sự kiện.
- Tìm hiểu chi phí và các trường hợp sử dụng phù hợp.
- Tiếp tục làm dự án LoveSpot, tập trung vào dữ liệu và kết nối giữa các thành phần.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Amazon SQS và cách lưu message trong Queue để xử lý sau. Xem ví dụ hệ thống xử lý đơn hàng. | 09/11/2026 | 09/11/2026 | [Amazon SQS](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html) |
| 3 | Tìm hiểu Standard Queue, FIFO Queue và Visibility Timeout. Đọc ví dụ về việc nhận, xử lý và xóa message. | 10/11/2026 | 10/11/2026 | [SQS Visibility Timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html) |
| 4 | Tìm hiểu Amazon SNS, Topic và Subscription. Xem cách một thông báo được gửi đến nhiều người nhận. | 11/11/2026 | 11/11/2026 | [Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/) |
| 5 | Tìm hiểu Amazon SES, cách gửi email từ ứng dụng và những giới hạn của SES Sandbox. Không gửi email thực tế. | 12/11/2026 | 12/11/2026 | [Amazon SES](https://docs.aws.amazon.com/ses/latest/dg/Welcome.html), [SES Sandbox](https://docs.aws.amazon.com/ses/latest/dg/request-production-access.html) |
| 6 | Tìm hiểu Amazon EventBridge, Event Bus, Rule và Target. **Làm dự án:** Xem lại dữ liệu địa điểm ăn uống và cách sử dụng dữ liệu này trong hệ thống gợi ý LoveSpot. | 13/11/2026 | 13/11/2026 | [Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html) |
| 7 | Ôn tập SQS, SNS, SES và EventBridge, kiểm tra bảng giá AWS. **Làm dự án:** Tìm hiểu cách kết nối Frontend, Backend và hệ thống gợi ý để chuẩn bị tích hợp các chức năng. | 14/11/2026 | 14/11/2026 | [AWS Messaging Decision Guide](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/sns-or-sqs-or-eventbridge.html), [EventBridge Pricing](https://aws.amazon.com/eventbridge/pricing/) |

### Kết quả đạt được tuần 9:

**Kiến thức đã tìm hiểu:**

- Hiểu SQS giúp lưu message trong Queue để hệ thống xử lý khi sẵn sàng.
- Phân biệt Standard Queue và FIFO Queue, hiểu cơ bản về Visibility Timeout.
- Biết SNS dùng Topic và Subscription để gửi thông báo đến nhiều nơi.
- Hiểu SES dùng để gửi email và có giới hạn khi tài khoản còn trong Sandbox.
- Biết EventBridge sử dụng Rule để chuyển sự kiện đến Target phù hợp.

**Tìm hiểu và luyện tập theo tài liệu:**

- Xem các ví dụ xử lý message bằng SQS và gửi thông báo qua SNS.
- So sánh SNS và EventBridge qua những tình huống đơn giản.
- Kiểm tra bảng giá AWS. Không tạo Queue, Topic, Event Rule hoặc gửi email thực tế để tránh phát sinh chi phí.

**Hoạt động dự án LoveSpot:**

- Xem lại cách tổ chức dữ liệu địa điểm ăn uống, đánh giá và những thông tin cần thiết cho hệ thống gợi ý.
- Tìm hiểu cách Frontend gửi thông tin người dùng đến Backend và nhận kết quả gợi ý.
- Chuẩn bị cho việc kết nối các thành phần của LoveSpot và kiểm tra chức năng trong những tuần tiếp theo.

**Khó khăn gặp phải và cách giải quyết:**

- Ban đầu chưa hiểu rõ Visibility Timeout vì message đã được nhận nhưng vẫn còn trong Queue. Sau khi xem ví dụ, tôi hiểu message cần được xóa khi xử lý xong.
- Dễ nhầm SNS với EventBridge. Tôi đọc thêm ví dụ và hiểu SNS thường dùng để gửi thông báo, còn EventBridge phù hợp khi cần lọc và chuyển sự kiện theo Rule.