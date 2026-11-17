---
title: "Worklog Tuần 12"
date: 2026-11-30
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

- Tìm hiểu Infrastructure as Code (IaC) và cách AWS CloudFormation hỗ trợ quản lý hạ tầng.
- Làm quen với CloudFormation Template, Stack và một số thành phần cơ bản trong file YAML.
- Hiểu tầm quan trọng của Backup & Recovery và các khái niệm RPO, RTO.
- Tìm hiểu AWS Backup và ôn lại những kiến thức AWS đã học trong 12 tuần.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Infrastructure as Code (IaC) và AWS CloudFormation. Đọc ví dụ dùng Template để quản lý tài nguyên thay vì tạo từng tài nguyên bằng tay. | 30/11/2026 | 30/11/2026 | [AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) |
| 3 | Tìm hiểu CloudFormation Template và Stack. Làm quen với file YAML cùng các phần Resources, Parameters và Outputs; chỉ đọc ví dụ, không tạo Stack. | 01/12/2026 | 01/12/2026 | [CloudFormation Template Sections](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html) |
| 4 | Tìm hiểu vì sao cần Backup dữ liệu. Xem các ví dụ Snapshot của EBS và sao lưu RDS để hiểu cách phục hồi khi xảy ra sự cố. | 02/12/2026 | 02/12/2026 | [Amazon EBS Snapshots](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-snapshots.html), [Amazon RDS Backup](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.BackupRestore.html) |
| 5 | Tìm hiểu AWS Backup, Backup Plan, Backup Vault và thời gian lưu bản sao lưu. Đọc về chi phí lưu trữ Backup, không tạo Backup Plan hoặc Snapshot thật. | 03/12/2026 | 03/12/2026 | [AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html), [Backup Plans](https://docs.aws.amazon.com/aws-backup/latest/devguide/about-backup-plans.html) |
| 6 | Tìm hiểu RPO và RTO qua ví dụ một website bị mất dữ liệu hoặc ngừng hoạt động. Đọc cách hai chỉ số này ảnh hưởng đến kế hoạch Backup & Recovery. | 04/12/2026 | 04/12/2026 | [Disaster Recovery Objectives](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/disaster-recovery-dr-objectives.html) |
| 7 | Ôn tập các chủ đề đã học từ EC2, S3, VPC đến Lambda, Database và Monitoring. Xem lại những điểm còn chưa rõ và đọc bảng giá CloudFormation, AWS Backup; không tạo tài nguyên mới. | 05/12/2026 | 05/12/2026 | [CloudFormation Pricing](https://aws.amazon.com/cloudformation/pricing/), [AWS Backup Pricing](https://aws.amazon.com/backup/pricing/) |

### Kết quả dự kiến tuần 12:

**Kiến thức cần nắm được:**

- Hiểu IaC là cách quản lý hạ tầng bằng file cấu hình thay vì làm mọi thao tác thủ công; CloudFormation giúp tạo và quản lý tài nguyên AWS theo Template.
- Biết Template mô tả tài nguyên cần tạo, còn Stack là nhóm tài nguyên được CloudFormation quản lý. Làm quen với Resources, Parameters và Outputs trong YAML.
- Hiểu Backup giúp giảm nguy cơ mất dữ liệu khi có sự cố; biết Snapshot và bản sao lưu Database là những cách bảo vệ dữ liệu thường gặp.
- Biết AWS Backup giúp quản lý việc sao lưu tập trung thông qua Backup Plan và Backup Vault.
- Phân biệt RPO là mức mất dữ liệu có thể chấp nhận, còn RTO là khoảng thời gian tối đa chấp nhận để khôi phục hệ thống.

**Ôn tập và tìm hiểu theo tài liệu:**

- Đọc một CloudFormation Template mẫu để nhận biết các phần chính, không tạo Stack hay EC2 thực tế.
- Xem ví dụ Backup cho EC2 và RDS, đồng thời ôn lại sự khác nhau giữa sao lưu dữ liệu và khôi phục dữ liệu.
- Tổng kết những kiến thức AWS đã học trong 12 tuần và đọc bảng giá. Không tạo Snapshot hoặc sử dụng AWS Backup thực tế để tránh phát sinh chi phí lưu trữ.

**Những điểm cần chú ý và cách tìm hiểu:**

- Cấu trúc YAML trong CloudFormation có nhiều phần nên có thể hơi khó đọc. Nên bắt đầu với Template ngắn và tập trung vào Resources trước, sau đó mới tìm hiểu Parameters và Outputs.
- RPO và RTO đều liên quan đến khôi phục nên cần phân biệt bằng ví dụ: RPO nói về lượng dữ liệu có thể mất, còn RTO nói về thời gian hệ thống có thể ngừng hoạt động.