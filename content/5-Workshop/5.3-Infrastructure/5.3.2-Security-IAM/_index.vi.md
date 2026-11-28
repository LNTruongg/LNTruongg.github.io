---
title: "Security Groups và IAM"
date: 2026-11-27
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---

#### Security Groups

1. Mở VPC Console → **Security groups → Create security group**. Nhập tên, mô tả và chọn `CoupleLifeAI-vpc`. Tạo lần lượt nhóm ALB, EC2 rồi RDS theo bảng. Trong **Inbound rules → Add rule**, chọn giao thức, port và Source. Với nguồn là security group, tìm tên nhóm vừa tạo. Giữ outbound mặc định cho bài thực hành.

| Tên | Inbound | Nguồn |
|---|---|---|
| CoupleLifeAI-SG-ALB | HTTP 80 | Ban đầu chưa mở; giới hạn origin CloudFront khi cấu hình ALB |
| CoupleLifeAI-SG-EC2 | TCP 8080 | CoupleLifeAI-SG-ALB |
| CoupleLifeAI-SG-RDS | TCP 5432 | CoupleLifeAI-SG-EC2 |

![Inbound rule EC2 từ ALB](./image_5.3.2/07.02-sg-ec2-configuration.png)
![Inbound rule RDS từ EC2](./image_5.3.2/08-sg-rds-configuration.png)

Không mở SSH 22, AI port 8000 hoặc PostgreSQL 5432 ra Internet. Outbound của app cần cho ECR, Secrets Manager và các API ngoài AWS. Giới hạn inbound ALB theo hướng dẫn mục 5.4.3.

#### IAM Role cho EC2

1. Mở [IAM Roles](https://console.aws.amazon.com/iam/home#/roles), chọn **Create role → AWS service → EC2**.
2. Gắn `AmazonSSMManagedInstanceCore` và `AmazonEC2ContainerRegistryReadOnly`. Đặt tên `CoupleLifeAI-EC2-Role`.

![Managed policies ban đầu](./image_5.3.2/09.02-ec2-iam-role.png)
3. Sau khi có secrets, cấp `secretsmanager:GetSecretValue` cho đúng hai ARN application secrets. Có thể sử dụng mẫu JSON dưới đây với account ID của tài khoản thực hành; thay `ACCOUNT_ID` trước khi sử dụng. Không cấp quyền đọc mọi secret trong tài khoản.

```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": "secretsmanager:GetSecretValue",
    "Resource": [
      "arn:aws:secretsmanager:ap-southeast-1:ACCOUNT_ID:secret:couplelife/production/backend-*",
      "arn:aws:secretsmanager:ap-southeast-1:ACCOUNT_ID:secret:couplelife/production/ai-service-*"
    ]
  }]
}
```

Trong IAM → Roles, mở `CoupleLifeAI-EC2-Role`, chọn Add permissions → Create inline policy → JSON. Dán policy, thay `ACCOUNT_ID` bằng kết quả ở mục 5.2, chọn Next rồi Create policy. Sau khi tạo RDS, vào RDS → Databases → `couplelife-db` → Configuration để tìm ARN master secret; cấp quyền `secretsmanager:GetSecretValue` cho đúng ARN đó trong policy bootstrap riêng.

Đặt tên inline policy `CoupleLifeSecretsRuntimePolicy`. Tạo policy tạm `CoupleLifeBootstrapRDSPolicy` chỉ cho phép đọc master secret RDS dùng trong bước khởi tạo. Sau migration và seed, thu hồi policy tạm; ứng dụng runtime sử dụng DB user riêng.

![IAM permissions trong giai đoạn bootstrap](./image_5.3.2/13-ec2-iam-permissions-final.png)

#### Secrets Manager

Sau khi tạo RDS ở mục 5.3.3, mở **Secrets Manager → Store a new secret → Other type of secret**. Tạo hai secret application và giữ nguyên secret do RDS quản lý.

| Secret name | Các key cần có |
|---|---|
| couplelife/production/ai-service | INTERNAL_API_SECRET, CLOUDFLARE_ACCOUNT_ID, CLOUDFLARE_API_TOKEN, GROQ_API_KEY; ROUTING_PROVIDER_URL nếu cấu hình yêu cầu |
| couplelife/production/backend | SECRET_KEY, INTERNAL_TOKEN, DATABASE_URL, CORS_ORIGINS |

`INTERNAL_TOKEN` và `INTERNAL_API_SECRET` phải giống nhau và là chuỗi ASCII ngẫu nhiên đủ mạnh; `SECRET_KEY` là chuỗi riêng. `DATABASE_URL` sử dụng DB user ứng dụng `couplelife_app`, tên database `couplelife_db` và endpoint RDS. Nếu mật khẩu có ký tự đặc biệt, mã hóa URL đúng cách. Không dùng master password trong runtime. Với HTTPS cùng origin `/api/*`, frontend không cần gọi domain ALB từ trình duyệt.

Trong RDS → Databases → `couplelife-db` → Connectivity & security, sao chép Endpoint. Tạo mật khẩu riêng cho `couplelife_app`; dùng cùng mật khẩu khi khởi tạo DB. Ví dụ định dạng `DATABASE_URL`: `postgresql+psycopg2://couplelife_app:PASSWORD@RDS_ENDPOINT:5432/couplelife_db?sslmode=require` (thay PASSWORD đã URL-encode và endpoint). Tạo token ngẫu nhiên bằng `python -c "import secrets; print(secrets.token_hex(32))"` trong terminal riêng; tạo hai giá trị độc lập cho token nội bộ và SECRET_KEY. Cấu hình CORS_ORIGINS theo định dạng mà mã nguồn Backend yêu cầu; cập nhật domain HTTPS của CloudFront ở mục 5.4.4 nếu cần. Không dùng wildcard với credentials.

Chọn key `aws/secretsmanager`, thêm tag Project = CoupleLifeAI, không replicate sang Region khác. Tạo secret, sau đó kiểm tra danh sách. Không hiển thị hoặc chia sẻ giá trị bí mật.

![Hai application secrets và RDS-managed secret](./image_5.3.2/12-secrets-manager-created.png)

#### Cấu hình Gmail SMTP

1. Mở AWS Secrets Manager.
2. Chọn secret `couplelife/production/backend`.
3. Chọn Retrieve secret value → Edit.
4. Bổ sung hai trường:
   - `SMTP_USER`: Địa chỉ Gmail gửi email.
   - `SMTP_PASSWORD`: Google App Password.
5. Chọn Save.

Backend sử dụng thông tin này để gửi email OTP khi người dùng quên mật khẩu.

![Cấu hình SMTP trong Secrets Manager](./image_5.3.2/smtp-secrets-manager.png)

**Lưu ý:** Nhập giá trị thật cho từng key; không dùng chuỗi mô tả hoặc placeholder. Xem mục 5.5.1 nếu AI Service trả lỗi 500.
