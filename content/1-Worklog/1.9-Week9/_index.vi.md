
---
title: "Worklog Tuần 9"
date: 2026-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

- Tìm hiểu cách các dịch vụ AWS gửi và nhận thông điệp (message).
- Làm quen với Amazon SQS, SNS và SES cùng những trường hợp sử dụng cơ bản.
- Hiểu Amazon EventBridge giúp các dịch vụ phản ứng với sự kiện như thế nào.
- Biết khi nào nên dùng từng dịch vụ và lưu ý chi phí trước khi thực hành.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Amazon SQS và cách message được lưu trong Queue để hệ thống xử lý sau. Xem ví dụ hàng đợi đơn hàng của một website. | 09/11/2026 | 09/11/2026 | [Amazon SQS](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html) |
| 3 | Tìm hiểu Standard Queue, FIFO Queue và Visibility Timeout. Đọc ví dụ vì sao message cần được xóa sau khi xử lý xong. | 10/11/2026 | 10/11/2026 | [SQS Visibility Timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html) |
| 4 | Tìm hiểu Amazon SNS, Topic và Subscription. Xem ví dụ một thông báo được gửi đến nhiều người nhận hoặc dịch vụ khác nhau. | 11/11/2026 | 11/11/2026 | [Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/) |
| 5 | Tìm hiểu Amazon SES và cách ứng dụng gửi email xác nhận hoặc thông báo. Đọc về xác minh email và giới hạn gửi trong Sandbox; không gửi email thực tế. | 12/11/2026 | 12/11/2026 | [Amazon SES](https://docs.aws.amazon.com/ses/latest/dg/Welcome.html), [SES Sandbox](https://docs.aws.amazon.com/ses/latest/dg/request-production-access.html) |
| 6 | Tìm hiểu Amazon EventBridge, Event Bus, Rule và Target. Xem ví dụ một sự kiện từ AWS được chuyển đến Lambda hoặc SQS khi khớp điều kiện. | 13/11/2026 | 13/11/2026 | [Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html) |
| 7 | Ôn tập và so sánh SQS, SNS, SES với EventBridge bằng các ví dụ đơn giản. Đọc thêm về mức giá và Free Tier; không tạo Queue, Topic hay Event Rule trên AWS. | 14/11/2026 | 14/11/2026 | [AWS Messaging Decision Guide](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/sns-or-sqs-or-eventbridge.html), [EventBridge Pricing](https://aws.amazon.com/eventbridge/pricing/) |

### Kết quả đạt được tuần 9:

**Kiến thức đã tìm hiểu:**

- Hiểu SQS là dịch vụ hàng đợi giúp lưu message để bên nhận lấy ra xử lý khi sẵn sàng, không cần hai bên hoạt động cùng lúc.
- Biết Standard Queue phù hợp với nhiều tác vụ thông thường, còn FIFO Queue phù hợp khi cần giữ thứ tự message theo nhóm. Hiểu cơ bản về Visibility Timeout.
- Biết SNS sử dụng Topic và Subscription để gửi một thông báo đến nhiều nơi, ví dụ email hoặc SQS.
- Hiểu SES dùng để gửi email từ ứng dụng, như email xác nhận đăng ký; tài khoản ở Sandbox có giới hạn người nhận và cần xác minh địa chỉ phù hợp.
- Biết EventBridge nhận sự kiện và dùng Rule để chuyển đến Target phù hợp, chẳng hạn Lambda hoặc SQS.

**Ôn tập và tìm hiểu theo tài liệu:**

- Xem ví dụ hệ thống đặt hàng dùng SQS để xử lý đơn hàng lần lượt theo khả năng của bên nhận.
- So sánh cách SNS gửi thông báo và EventBridge chọn nơi nhận sự kiện theo điều kiện.
- Kiểm tra thông tin giá và hạn mức miễn phí. Tuần này chỉ đọc tài liệu, không tạo tài nguyên hoặc gửi email trên AWS để tránh chi phí ngoài dự kiến.

**Khó khăn gặp phải và cách giải quyết:**

- Phần Visibility Timeout phải đọc lại kỹ vì message đã được nhận nhưng chưa biến mất khỏi Queue. Xem ví dụ về việc xử lý xong mới xóa message giúp tôi hiểu rõ hơn cơ chế này.
- SNS và EventBridge đều có thể chuyển thông tin đến nhiều dịch vụ nên khá khó chọn khi nào dùng cái nào. Sau khi xem các ví dụ, tôi hiểu SNS phù hợp để gửi thông báo theo Topic, còn EventBridge hữu ích khi cần lọc sự kiện theo Rule.
