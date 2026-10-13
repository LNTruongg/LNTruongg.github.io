---
title: "Worklog Tuần 2"
date: 2026-09-22
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

- Tìm hiểu chuyên sâu hơn về Amazon EC2, các mô hình tính phí và dịch vụ lưu trữ Amazon EBS.
- Thực hành quản lý dung lượng ổ đĩa trên EC2 Windows Server.
- Hiểu cách quản lý tài nguyên AWS 
- Cài đặt và làm quen với AWS CLI để tương tác với các dịch vụ AWS thông qua dòng lệnh.
- Tìm hiểu Amazon S3 và thực hành các thao tác lưu trữ dữ liệu cơ bản.

### Các công việc đã thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
|---|---|---|---|---|
| 3 | Đến văn phòng AWS, tham quan môi trường làm việc, làm quen với mentors và các thành viên trong lớp. | 2026-09-22 | 2026-09-22 | AWS Office |
| 4 Tìm hiểu EC2 Pricing, các use case và các loại EBS Volume thường dùng. Thực hành gắn thêm EBS Volume vào EC2 Windows Server, khởi tạo và mount ổ đĩa, tạo các file văn bản và thay đổi dung lượng Volume trên AWS Console. | 2026-09-23 | 2026-09-23 | [AWS EC2 Tutorial](https://www.youtube.com/watch?v=ILQeF7Z-Sis) |
| 5 | Kiểm tra và terminate các EC2 Instance đã tạo trong quá trình thực hành để tránh phát sinh thêm chi phí. Tìm hiểu thêm về quản lý tài nguyên AWS. | 2026-09-24 | 2026-09-24 | [AWS Roadmap](https://roadmap.sh/aws), [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| 6 | Cài đặt AWS CLI trên máy tính cá nhân, kiểm tra phiên bản và tìm hiểu cách sử dụng Access Key để cấu hình AWS CLI. Đọc tài liệu giới thiệu về Amazon S3. | 2026-09-25 | 2026-09-25 | [AWS CLI Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) |
| 7 | Tìm hiểu khái niệm, tính năng và các trường hợp sử dụng Amazon S3. Thực hành tạo S3 Bucket, tạo Folder, Upload, Download và Delete các file. | 2026-09-26 | 2026-09-26 | [AWS Roadmap](https://roadmap.sh/aws), [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được trong tuần 2:

- **Kiến thức đã nắm được:**
  - EC2 Pricing và các trường hợp sử dụng Amazon EC2.
  - Các loại Amazon EBS Volume và cách quản lý dung lượng lưu trữ.
  - Quản lý vòng đời EC2 Instance và kiểm soát chi phí AWS.
  - Cài đặt và cấu hình AWS CLI cơ bản.
  - Khái niệm Amazon S3, Bucket, Object và các thao tác lưu trữ dữ liệu.

- **Thực hành Amazon EC2 và EBS:**
  - Tìm hiểu các mô hình tính phí EC2 và các loại EBS Volume phổ biến.
  - Gắn thêm EBS Volume vào EC2 Windows Server.
  - Khởi tạo và mount ổ đĩa mới trên Windows Server.
  - Tạo và thao tác với các file văn bản trên ổ đĩa.
  - Thực hành thay đổi dung lượng EBS Volume trên AWS Management Console.
  - Hiểu cách mở rộng dung lượng lưu trữ khi máy chủ thiếu không gian mà không cần tạo lại EC2 Instance.

- **Quản lý tài nguyên và chi phí AWS:**
  - Ghi nhận khoảng 3,2 USD chi phí phát sinh trong quá trình thử nghiệm EC2.
  - Terminate các EC2 Instance không còn sử dụng.
  - Nhận thức được tầm quan trọng của việc kiểm tra tài nguyên và theo dõi chi phí khi sử dụng AWS.

- **Cài đặt và tìm hiểu AWS CLI:**
  - Cài đặt AWS CLI trên máy tính cá nhân.
  - Biết cách kiểm tra phiên bản AWS CLI.
  - Tìm hiểu cách sử dụng Access Key để cấu hình thông tin xác thực khi làm việc với AWS CLI.

- **Thực hành Amazon S3:**
  - Hiểu Amazon S3 là dịch vụ lưu trữ đối tượng trên AWS.
  - Tạo S3 Bucket.
  - Tạo Folder và Upload các file lên S3.
  - Download file từ S3 về máy tính.
  - Xóa các file đã lưu trữ trên S3.
  - Hiểu các trường hợp sử dụng S3 để lưu trữ nhiều loại dữ liệu khác nhau.

- **Khó khăn gặp phải:**
  - EC2 Windows Server phản hồi khá chậm, gây khó khăn trong quá trình thao tác và thực hành.
  - Việc Upload nhiều file cùng lúc lên S3 mất khá nhiều thời gian, nên chủ yếu thực hiện Upload từng file.
  - Phát sinh chi phí khi thử nghiệm EC2, từ đó rút ra kinh nghiệm cần theo dõi tài nguyên và chi phí AWS thường xuyên.
