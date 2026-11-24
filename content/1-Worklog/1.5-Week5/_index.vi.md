---
title: "Worklog Tuần 5"
date: 2026-10-12
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

- Tìm hiểu Load Balancing và lý do cần phân phối lưu lượng truy cập giữa nhiều máy chủ.
- Làm quen với Elastic Load Balancing, đặc biệt là Application Load Balancer (ALB).
- Hiểu vai trò của Listener, Target Group và Health Check trong ALB.
- Tìm hiểu Auto Scaling Group (ASG), Launch Template và cách điều chỉnh số lượng EC2 theo nhu cầu.
- Phân tích mô hình kết hợp ALB và ASG ở mức cơ bản, đồng thời tìm hiểu chi phí trước khi thực hành.
- Tiếp tục tìm hiểu dự án LoveSpot, tập trung vào bố cục giao diện và các chức năng chính của ứng dụng.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu khái niệm Load Balancing và Single Point of Failure. Tìm hiểu Elastic Load Balancing (ELB), mục đích sử dụng và sự khác nhau cơ bản giữa Application Load Balancer và Network Load Balancer. | 12/10/2026 | 12/10/2026 | [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html) |
| 3 | Tìm hiểu Application Load Balancer hoạt động ở Layer 7. Làm quen với Listener, Listener Rule và Target Group; xem ví dụ điều hướng request dựa trên URL path. | 13/10/2026 | 13/10/2026 | [Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/), [ALB Listeners](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html) |
| 4 | Tìm hiểu Health Check và cách ALB xác định Target Healthy hoặc Unhealthy. Phân tích sơ đồ luồng request từ Client qua ALB đến các EC2 trong Target Group ở nhiều Availability Zone. | 14/10/2026 | 14/10/2026 | [ALB Target Groups](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html), [Target Group Health Checks](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html) |
| 5 | Tìm hiểu sự khác nhau giữa Scale Up/Down và Scale Out/In. Làm quen với Amazon EC2 Auto Scaling, Auto Scaling Group và Launch Template, gồm các thông tin như AMI, Instance Type và Security Group. | 15/10/2026 | 15/10/2026 | [EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html), [Launch Templates](https://docs.aws.amazon.com/autoscaling/ec2/userguide/launch-templates.html) |
| 6 | Tìm hiểu ba thông số Minimum, Maximum và Desired Capacity của ASG. Đọc ví dụ về Target Tracking Scaling theo mức sử dụng CPU và cách ASG bổ sung EC2 khi cần thiết. | 16/10/2026 | 16/10/2026 | [ASG Scaling Limits](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-capacity-limits.html), [Target Tracking Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html) |
| 7 | Ôn tập và phác thảo sơ đồ ALB kết hợp ASG bằng draw.io. Tìm hiểu cách EC2 được thêm vào Target Group và kiểm tra bảng giá AWS; không tạo ALB hoặc ASG chạy EC2 để tránh phát sinh chi phí. **Làm dự án:** Tiếp tục phát triển ý tưởng LoveSpot, phác thảo bố cục giao diện và xác định các chức năng tìm kiếm, gợi ý địa điểm và tạo lịch trình. | 17/10/2026 | 17/10/2026 | [ALB with Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-load-balancer.html), [ELB Pricing](https://aws.amazon.com/elasticloadbalancing/pricing/), [EC2 Auto Scaling Pricing](https://aws.amazon.com/ec2/autoscaling/pricing/) |

### Kết quả đạt được tuần 5:

**Kiến thức đã tìm hiểu:**

- Hiểu Load Balancer giúp phân phối request đến nhiều máy chủ, hạn chế phụ thuộc vào một EC2 duy nhất và cải thiện khả năng phục vụ của ứng dụng.
- Biết Elastic Load Balancing có nhiều loại; trong đó Application Load Balancer phù hợp với ứng dụng HTTP/HTTPS, còn Network Load Balancer hoạt động chủ yếu ở Layer 4.
- Hiểu luồng xử lý cơ bản `Client → ALB → Listener Rule → Target Group → EC2` và cách ALB điều hướng request theo đường dẫn URL.
- Biết Health Check giúp ALB theo dõi trạng thái Target để phân phối request đến các Target đang hoạt động bình thường.
- Phân biệt Scale Up/Down là thay đổi cấu hình máy chủ, còn Scale Out/In là tăng hoặc giảm số lượng máy chủ.
- Hiểu ASG sử dụng Launch Template để xác định cấu hình EC2 và duy trì số lượng Instance theo Desired Capacity, trong giới hạn Minimum và Maximum.
- Làm quen với Target Tracking Scaling và vai trò của CloudWatch Metrics trong việc hỗ trợ tự động mở rộng hệ thống.

**Tìm hiểu và luyện tập theo tài liệu:**

- Phân tích ví dụ một website có hai EC2 phía sau ALB để hình dung cách phân phối request và tình huống một Target không vượt qua Health Check.
- Phác thảo bằng draw.io mô hình đơn giản gồm Client, ALB, Target Group và các EC2 thuộc Auto Scaling Group, liên hệ với kiến thức VPC và Availability Zone từ những tuần trước.
- Luyện tập với ví dụ giả định `Min = 1`, `Desired = 2`, `Max = 3` để hiểu ASG có thể điều chỉnh số lượng EC2 như thế nào.
- Đọc hướng dẫn kết hợp ALB với ASG thay vì trực tiếp chạy bài lab tạo nhiều EC2.
- Tìm hiểu chi phí của ALB, EC2 và các tài nguyên liên quan. Tuần này chỉ học và phân tích sơ đồ, không triển khai hệ thống thực tế để tránh phát sinh chi phí ngoài dự kiến.

**Hoạt động dự án LoveSpot:**

- Tiếp tục tìm hiểu cách xây dựng giao diện LoveSpot, ứng dụng hỗ trợ gợi ý địa điểm ăn uống và lập lịch trình tại TP. Hồ Chí Minh.
- Phác thảo bố cục các màn hình chính, tập trung vào việc nhập thông tin, tìm kiếm địa điểm và hiển thị những gợi ý phù hợp với nhu cầu người dùng.
- Xem xét cách người dùng chuyển từ bước lựa chọn địa điểm sang tạo lịch trình, nhằm giúp các chức năng có luồng sử dụng rõ ràng và dễ thao tác.
- Bước đầu xác định những dữ liệu cần thiết cho hệ thống gợi ý, chẳng hạn thông tin địa điểm, khu vực và sở thích của người dùng. Đây vẫn là giai đoạn chuẩn bị, chưa triển khai hạ tầng AWS cho LoveSpot.

**Khó khăn gặp phải và cách giải quyết:**

- Ban đầu dễ nhầm Listener với Target Group vì cả hai đều tham gia xử lý request trong ALB. Sau khi vẽ lại luồng request, tôi hiểu Listener nhận kết nối và xét Rule, còn Target Group chứa các Target được chọn để xử lý request.
- Chưa phân biệt rõ vai trò của Load Balancer và Auto Scaling Group vì cả hai đều liên quan đến khả năng mở rộng. Việc so sánh từng nhiệm vụ trong sơ đồ giúp tôi hiểu rằng ALB phân phối lưu lượng, còn ASG quản lý số lượng EC2 theo nhu cầu.