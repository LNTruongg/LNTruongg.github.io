---
title: "Worklog Tuần 12"
date: 2026-11-30
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

- Tìm hiểu Infrastructure as Code (IaC) và cách AWS CloudFormation hỗ trợ quản lý hạ tầng thông qua các file cấu hình.
- Làm quen với CloudFormation Template, Stack và các thành phần cơ bản như Resources, Parameters và Outputs.
- Hiểu tầm quan trọng của Backup & Recovery, AWS Backup và các khái niệm RPO, RTO.
- Ôn tập các kiến thức AWS trọng tâm đã học trong chương trình.
- **Làm dự án:** Tiếp tục hoàn thiện ứng dụng gợi ý quán ăn và tạo lịch trình tại TP.HCM.
- **Làm dự án:** Kiểm thử tổng thể luồng hoạt động từ thông tin người dùng đến kết quả gợi ý và lịch trình.
- **Làm dự án:** Rà soát dữ liệu địa điểm, cải thiện chất lượng gợi ý và trải nghiệm người dùng.
- **Làm dự án:** Chuẩn bị bản demo, tổng hợp kết quả và xác định những hạn chế cần tiếp tục cải thiện.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Infrastructure as Code (IaC) và AWS CloudFormation. Làm quen với Template, Stack và các thành phần Resources, Parameters, Outputs trong YAML. Đọc ví dụ quản lý tài nguyên AWS bằng Template thay vì tạo thủ công; không tạo Stack thực tế. | 30/11/2026 | 30/11/2026 | [AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html), [CloudFormation Template Sections](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html) |
| 3 | Tìm hiểu Backup & Recovery, AWS Backup và các phương pháp sao lưu như EBS Snapshot, RDS Backup. Phân biệt RPO và RTO qua các tình huống mất dữ liệu hoặc gián đoạn hệ thống. Ôn tập kiến thức AWS và lưu ý chi phí, không tạo tài nguyên sao lưu thực tế. | 01/12/2026 | 01/12/2026 | [AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html), [Amazon RDS Backup](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.BackupRestore.html), [Disaster Recovery Objectives](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/disaster-recovery-dr-objectives.html) |
| 4 | **Làm dự án:** Rà soát tổng thể ứng dụng gợi ý quán ăn và tạo lịch trình tại TP.HCM. Kiểm tra luồng xử lý từ việc người dùng nhập ngân sách, sở thích, khu vực và thời gian đến khi hệ thống trả về danh sách quán ăn và lịch trình đề xuất. | 02/12/2026 | 02/12/2026 | Source code Frontend, Backend và hệ thống gợi ý của dự án |
| 5 | **Làm dự án:** Kiểm tra chất lượng dữ liệu địa điểm và kết quả gợi ý. Chú ý các trường hợp địa điểm thiếu tọa độ GPS, thông tin không hợp lệ, quán ăn không phù hợp với ngân sách hoặc khoảng cách quá xa. Rà soát cách lựa chọn và sắp xếp địa điểm trong lịch trình. | 03/12/2026 | 03/12/2026 | Dataset địa điểm, tài liệu xử lý dữ liệu và các tình huống kiểm thử |
| 6 | **Làm dự án:** Kiểm thử việc kết nối giữa Frontend, Backend và hệ thống gợi ý. Kiểm tra khả năng hiển thị thông tin địa điểm, lịch trình và bản đồ. Xem xét các trường hợp dữ liệu đầu vào không hợp lệ, không tìm được quán phù hợp hoặc API trả về lỗi để xác định hướng cải thiện trải nghiệm người dùng. | 04/12/2026 | 04/12/2026 | Source code dự án, API và tài liệu kiểm thử |
| 7 | **Làm dự án:** Chuẩn bị và chạy thử bản demo ứng dụng trên môi trường local. Kiểm tra các chức năng chính, tổng hợp kết quả kiểm thử và ghi nhận những vấn đề còn tồn tại. Rà soát tài liệu giới thiệu dự án và xác định các công việc cần tiếp tục thực hiện sau giai đoạn này. | 05/12/2026 | 05/12/2026 | Source code, tài liệu dự án và checklist kiểm thử demo |

### Kết quả dự kiến tuần 12:

**Kiến thức AWS cần nắm được:**

- Hiểu Infrastructure as Code (IaC) là phương pháp quản lý hạ tầng thông qua mã và file cấu hình thay vì thực hiện hoàn toàn bằng thao tác thủ công.
- Biết AWS CloudFormation sử dụng Template để mô tả tài nguyên và Stack để quản lý các tài nguyên được triển khai.
- Làm quen với cấu trúc YAML và các thành phần Resources, Parameters và Outputs.
- Hiểu vai trò của Backup & Recovery trong việc hạn chế mất dữ liệu và giảm thời gian gián đoạn khi xảy ra sự cố.
- Biết AWS Backup hỗ trợ quản lý sao lưu tập trung cho các tài nguyên được hỗ trợ.
- Phân biệt RPO là mức mất dữ liệu có thể chấp nhận và RTO là khoảng thời gian tối đa chấp nhận để khôi phục hệ thống.
- Tổng kết những kiến thức AWS đã học và hiểu tầm quan trọng của việc lựa chọn dịch vụ dựa trên nhu cầu và chi phí thực tế.

**Kết quả dự kiến đối với dự án:**

- **Làm dự án:** Kiểm tra được luồng hoạt động chính của ứng dụng từ thông tin đầu vào đến kết quả gợi ý quán ăn và lịch trình.
- **Làm dự án:** Xác định các trường hợp dữ liệu địa điểm không hợp lệ có thể ảnh hưởng đến kết quả gợi ý và hiển thị bản đồ.
- **Làm dự án:** Đánh giá mức độ phù hợp của các địa điểm dựa trên sở thích, ngân sách, vị trí và khoảng cách di chuyển.
- **Làm dự án:** Rà soát việc trao đổi dữ liệu giữa Frontend, Backend và hệ thống gợi ý, đồng thời ghi nhận các vấn đề phát sinh trong quá trình kiểm thử.
- **Làm dự án:** Kiểm tra các chức năng chính và cải thiện những vấn đề ảnh hưởng đến trải nghiệm người dùng trong phạm vi thời gian cho phép.
- **Làm dự án:** Chuẩn bị bản demo local để giới thiệu mục tiêu, cách sử dụng và các chức năng đã hoàn thiện của ứng dụng.
- **Làm dự án:** Tổng hợp những kết quả đạt được, các hạn chế còn tồn tại và hướng phát triển tiếp theo của hệ thống.

**Những điểm cần chú ý và cách giải quyết:**

- **Kiến thức AWS:** CloudFormation và AWS Backup có nhiều khái niệm liên quan đến hạ tầng. Ưu tiên hiểu nguyên lý, đọc ví dụ và kiểm soát chi phí thay vì tạo tài nguyên không cần thiết.
- **Làm dự án — Chất lượng dữ liệu:** Dữ liệu địa điểm thiếu hoặc sai tọa độ GPS có thể ảnh hưởng đến việc xác định khoảng cách và hiển thị bản đồ. Cần kiểm tra tính hợp lệ trước khi sử dụng.
- **Làm dự án — Chất lượng lịch trình:** Các địa điểm được gợi ý cần đáp ứng nhu cầu người dùng và có thứ tự di chuyển hợp lý, không chỉ dựa trên đánh giá của quán.
- **Làm dự án — Tích hợp hệ thống:** Cần kiểm tra sự thống nhất dữ liệu giữa Frontend, Backend và hệ thống gợi ý để hạn chế lỗi trong quá trình xử lý yêu cầu.
- **Làm dự án — Trải nghiệm người dùng:** Cần xử lý phù hợp các tình huống thiếu thông tin đầu vào, không tìm thấy địa điểm hoặc kết quả gợi ý không đáp ứng điều kiện.
- **Làm dự án — Chuẩn bị demo:** Ưu tiên kiểm thử các chức năng chính, ghi nhận rõ những tính năng đã hoàn thiện và những phần còn đang phát triển.
- **Làm dự án — Triển khai:** Tập trung hoàn thiện và kiểm thử ứng dụng trên môi trường local. Việc triển khai AWS sẽ được cân nhắc riêng dựa trên yêu cầu kỹ thuật và chi phí.
