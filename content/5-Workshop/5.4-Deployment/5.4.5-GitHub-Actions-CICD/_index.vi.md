
---
title: "CI/CD với GitHub Actions"
date: 2026-11-28
weight: 5
chapter: false
pre: " <b> 5.4.5. </b> "
---

#### 1. Cấu hình GitHub Actions

GitHub Actions giúp tự động hóa quá trình kiểm thử, đóng gói và triển khai ứng dụng lên AWS mỗi khi mã nguồn được cập nhật.

Pipeline gồm hai giai đoạn chính:

- **Continuous Integration (CI):** Kiểm thử Backend, build Frontend và kiểm tra Docker images.
- **Continuous Deployment (CD):** Đẩy Docker images lên Amazon ECR, cập nhật Frontend trên Amazon S3 và triển khai phiên bản mới trên Amazon EC2.

#### 2. Cấu hình xác thực AWS bằng OIDC

1. Truy cập AWS Management Console, mở dịch vụ **IAM**.
2. Chọn **Identity providers**, sau đó chọn **Add provider**.
3. Chọn OpenID Connect và nhập:
   - Provider URL: `https://token.actions.githubusercontent.com`
   - Audience: `sts.amazonaws.com`
4. Tạo IAM Role dành cho GitHub Actions.
5. Cấu hình Trust Policy giới hạn quyền truy cập đúng repository và branch hoặc production environment được sử dụng.
6. Cấp các quyền cần thiết để triển khai thông qua Amazon ECR, Amazon S3, CloudFront, Systems Manager và các tài nguyên liên quan.

OIDC cho phép GitHub Actions sử dụng thông tin xác thực tạm thời thay vì lưu AWS Access Key dài hạn trong repository.

#### 3. Tạo workflow CI/CD

1. Tải [workflow CI/CD](./attachments/deploy-aws.yml.txt).
2. Trong repository, tạo thư mục `.github/workflows/` và lưu nội dung thành `deploy-aws.yml`.
3. Cập nhật các thông số AWS trong workflow phù hợp với tài khoản và tài nguyên đã tạo:
   - AWS Region.
   - IAM Role ARN.
   - ECR repositories.
   - S3 bucket.
   - CloudFront Distribution ID.
   - EC2, Auto Scaling Group và Target Group.
   - Health Check URL.
4. Kiểm tra branch trong `on.push.branches` khớp với branch triển khai.
5. Commit và push mã nguồn lên GitHub.
6. Mở tab **Actions**, chọn workflow CI/CD để theo dõi quá trình thực thi.

#### 4. Quy trình triển khai tự động

Sau khi mã nguồn được push, GitHub Actions thực hiện các công việc sau:

1. Chạy Backend automated tests.
2. Build Frontend SPA.
3. Kiểm tra khả năng build Docker images.
4. Xác thực với AWS thông qua OIDC.
5. Build và push Docker images lên Amazon ECR.
6. Đồng bộ Frontend lên Amazon S3 và làm mới bộ nhớ đệm CloudFront.
7. Thực hiện PostgreSQL database migration bằng Alembic.
8. Cập nhật Backend và AI Service lần lượt trên các EC2 instances thông qua AWS Systems Manager.
9. Kiểm tra trạng thái ALB targets và API Health Check.

Rolling Deployment giúp hạn chế gián đoạn dịch vụ bằng cách cập nhật từng EC2 instance thay vì cập nhật đồng thời toàn bộ hệ thống.

Nếu quá trình cập nhật không đạt yêu cầu kiểm tra sức khỏe, cơ chế rollback sẽ khôi phục phiên bản Docker image trước đó.

#### 5. Kiểm tra kết quả CI/CD

Trong GitHub Actions, mở workflow run và kiểm tra cả hai job:

- **CI — Tests, Security & Docker Build:** Success.
- **CD — Deploy to AWS EC2 (Singapore):** Success.

![GitHub Actions CI/CD triển khai thành công](./image_5.4.5/01-github-actions-ci-cd-success.png)

Trong lần triển khai minh họa:

| Hạng mục | Kết quả |
|---|---|
| Backend automated tests | 156/156 Passed |
| Continuous Integration | Success |
| Continuous Deployment | Success |
| Thời gian CI | 2 phút 18 giây |
| Thời gian CD | 3 phút 57 giây |
| Tổng thời gian | 6 phút 21 giây |

#### 6. Kiểm tra ứng dụng sau triển khai

1. Mở Amazon EC2, chọn **Target Groups**.
2. Chọn Target Group của ứng dụng và kiểm tra các instances đều có trạng thái **Healthy**.
3. Truy cập CloudFront Distribution Domain Name để kiểm tra giao diện website.
4. Kiểm tra API tại đường dẫn `/api/v1/health`.
5. Thử nghiệm các chức năng của ứng dụng để xác nhận phiên bản mới hoạt động bình thường.

Sau khi hoàn thành, hệ thống có thể tự động kiểm thử và triển khai phiên bản mới thông qua GitHub Actions mà không cần cập nhật từng EC2 instance bằng phương pháp thủ công.
