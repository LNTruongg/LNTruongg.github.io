---
title: "Worklog Tuần 11"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

- Tìm hiểu AWS Elastic Beanstalk và cách dịch vụ này hỗ trợ triển khai ứng dụng web.
- Làm quen với Docker, Docker Image, Container và vai trò của Amazon ECR, Amazon ECS.
- Hiểu những thành phần cơ bản của ECS và lưu ý chi phí khi triển khai ứng dụng trên AWS.
- **Làm dự án:** Tiếp tục phát triển hệ thống gợi ý quán ăn và tạo lịch trình tại TP.HCM.
- **Làm dự án:** Rà soát việc kết nối giữa dữ liệu địa điểm, hệ thống gợi ý, Backend và Frontend.
- **Làm dự án:** Kiểm tra kết quả gợi ý, khả năng xây dựng lịch trình và xử lý các tình huống dữ liệu không phù hợp.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu AWS Elastic Beanstalk, các khái niệm Application, Environment và Platform. Xem cách triển khai ứng dụng web và những tài nguyên có thể phát sinh chi phí. | 23/11/2026 | 23/11/2026 | [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html), [Elastic Beanstalk Concepts](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html) |
| 3 | Tìm hiểu Docker Image và Container. Làm quen với Amazon ECR để lưu trữ Image và Amazon ECS để chạy, quản lý Container. Đọc về Cluster, Task Definition, Service và Fargate; chưa tạo tài nguyên AWS thực tế. | 24/11/2026 | 24/11/2026 | [Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html), [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) |
| 4 | **Làm dự án:** Rà soát kiến trúc của ứng dụng gợi ý quán ăn và tạo lịch trình tại TP.HCM. Kiểm tra vai trò của Frontend, Backend, hệ thống gợi ý và nguồn dữ liệu địa điểm. Xác định những thành phần cần kết nối để tạo ra một lịch trình hoàn chỉnh. | 25/11/2026 | 25/11/2026 | Source code và tài liệu kiến trúc dự án |
| 5 | **Làm dự án:** Kiểm tra luồng dữ liệu từ yêu cầu người dùng đến hệ thống gợi ý. Rà soát các thông tin như ngân sách, sở thích, khu vực và tọa độ GPS; kiểm tra cách dữ liệu địa điểm được truy xuất và cung cấp cho quá trình lựa chọn quán ăn. | 26/11/2026 | 26/11/2026 | Dataset, Backend API và tài liệu xử lý dữ liệu của dự án |
| 6 | **Làm dự án:** Tiếp tục xây dựng và kiểm tra quá trình tích hợp API giữa các thành phần của hệ thống. Xem xét định dạng dữ liệu đầu vào, đầu ra, kết quả gợi ý địa điểm và khả năng hiển thị lịch trình trên giao diện người dùng. | 27/11/2026 | 27/11/2026 | Source code Frontend, Backend và hệ thống gợi ý |
| 7 | **Làm dự án:** Kiểm thử luồng gợi ý và tạo lịch trình với nhiều tình huống khác nhau. Đánh giá mức độ phù hợp của quán ăn, khoảng cách giữa các địa điểm và thứ tự di chuyển. Ghi nhận lỗi hoặc hạn chế để tiếp tục cải thiện trong tuần tiếp theo. | 28/11/2026 | 28/11/2026 | Source code, dữ liệu và các tình huống kiểm thử dự án |

### Kết quả dự kiến tuần 11:

**Kiến thức AWS cần nắm được:**

- Hiểu AWS Elastic Beanstalk hỗ trợ đơn giản hóa việc triển khai và quản lý ứng dụng web, nhưng tài nguyên hạ tầng được sử dụng vẫn có thể phát sinh chi phí.
- Phân biệt Docker Image là bản đóng gói ứng dụng và Container là môi trường chạy được tạo từ Image.
- Hiểu Amazon ECR được sử dụng để lưu trữ Container Image, còn Amazon ECS hỗ trợ chạy và quản lý Container.
- Làm quen với Cluster, Task Definition, Task, Service và hai lựa chọn chạy Container trên EC2 hoặc AWS Fargate.
- Có kiến thức nền tảng để cân nhắc phương án triển khai ứng dụng lên AWS trong tương lai.

**Kết quả dự kiến đối với dự án:**

- **Làm dự án:** Hiểu rõ hơn cách các thành phần Frontend, Backend, hệ thống gợi ý và dữ liệu địa điểm phối hợp với nhau.
- **Làm dự án:** Xác định luồng xử lý từ thông tin người dùng đến kết quả đề xuất quán ăn và lịch trình.
- **Làm dự án:** Rà soát dữ liệu địa điểm và việc sử dụng tọa độ GPS trong quá trình gợi ý, hiển thị bản đồ.
- **Làm dự án:** Kiểm tra khả năng trao đổi dữ liệu qua API giữa các thành phần và xác định những điểm cần cải thiện.
- **Làm dự án:** Có các tình huống kiểm thử để đánh giá chất lượng gợi ý và tính hợp lý của lịch trình trước khi hoàn thiện dự án.

**Những điểm cần chú ý và cách giải quyết:**

- **Kiến thức AWS:** Elastic Beanstalk, ECR và ECS có vai trò khác nhau. Cần phân biệt dịch vụ hỗ trợ triển khai ứng dụng, dịch vụ lưu trữ Image và dịch vụ quản lý Container; đồng thời kiểm tra chi phí trước khi sử dụng.
- **Làm dự án — Tích hợp hệ thống:** Các thành phần Frontend, Backend và hệ thống gợi ý cần thống nhất cấu trúc dữ liệu đầu vào, đầu ra để tránh lỗi khi kết nối.
- **Làm dự án — Dữ liệu địa điểm:** Những quán ăn thiếu hoặc có tọa độ GPS không chính xác có thể ảnh hưởng đến bản đồ và lịch trình. Cần kiểm tra tính hợp lệ trước khi sử dụng.
- **Làm dự án — Chất lượng gợi ý:** Kết quả cần đáp ứng nhu cầu người dùng, đồng thời xem xét ngân sách, khoảng cách và sự phù hợp giữa các địa điểm.
- **Làm dự án — Kiểm thử:** Cần thử nhiều trường hợp đầu vào, ghi nhận lỗi và cải thiện dần thay vì chỉ đánh giá hệ thống trên một lịch trình mẫu.
- **Làm dự án — Phạm vi triển khai:** Ưu tiên tích hợp và kiểm thử các thành phần trên môi trường local. Việc triển khai lên AWS sẽ được xem xét riêng dựa trên yêu cầu thực tế và chi phí.