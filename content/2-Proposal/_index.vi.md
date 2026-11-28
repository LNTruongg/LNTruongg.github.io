---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
# CoupleLife AI – Intelligent Couple Activity Discovery & Itinerary Planning Platform

## Nền tảng hỗ trợ khám phá địa điểm và lập lịch trình cho các cặp đôi tại TP. Hồ Chí Minh

### 1. Tổng quan, mục tiêu và phạm vi

CoupleLife AI là nền tảng hỗ trợ các cặp đôi tìm kiếm địa điểm, lựa chọn hoạt động và lập lịch trình đi chơi tại TP. Hồ Chí Minh. Người dùng có thể tìm địa điểm theo sở thích, khám phá các điểm dừng dọc tuyến đường và điều chỉnh lịch trình theo thời gian, khoảng cách và ngân sách trên cùng một ứng dụng.

Hệ thống gồm giao diện React và Vite, Backend Gateway và AI Service phát triển bằng FastAPI. Dữ liệu địa điểm được kết hợp với dịch vụ định tuyến và mô hình AI để hỗ trợ tìm kiếm, xếp hạng và đề xuất lịch trình. Hệ thống được triển khai trên AWS tại Singapore, sử dụng EC2, RDS PostgreSQL Multi-AZ, S3 và CloudFront.

**Mục tiêu**

- Xây dựng ứng dụng web hỗ trợ khám phá địa điểm và lập lịch trình theo nhu cầu của người dùng.
- Kết hợp dữ liệu địa điểm, thông tin tuyến đường và AI để nâng cao chất lượng đề xuất.
- Thiết kế hạ tầng AWS có khả năng duy trì dịch vụ khi một máy chủ gặp sự cố, quản lý truy cập và bảo vệ dữ liệu người dùng.
- Tự động hóa kiểm thử và triển khai, theo dõi tình trạng hệ thống và kiểm soát chi phí vận hành.

**Phạm vi dự án**

- Đối tượng sử dụng: các cặp đôi có nhu cầu tìm kiếm địa điểm và lên kế hoạch đi chơi tại TP. Hồ Chí Minh.
- Chức năng: tìm kiếm POI, đề xuất địa điểm theo tuyến đường, quản lý điểm dừng, tối ưu lịch trình, kiểm tra thời gian và ngân sách, xác thực tài khoản và khôi phục mật khẩu qua email OTP.
- Hạ tầng: triển khai ứng dụng web, Backend, AI Service và cơ sở dữ liệu trên AWS; sử dụng GitHub Actions cho CI/CD.
- Kế hoạch vận hành ban đầu: 14 ngày, với ngân sách nội bộ 120 USD.

### 2. Vấn đề cần giải quyết

**Vấn đề**

Khi lên kế hoạch đi chơi, các cặp đôi thường phải tham khảo bản đồ, mạng xã hội và các trang đánh giá để tìm địa điểm phù hợp. Việc tính thời gian di chuyển, cân đối ngân sách và sắp xếp các điểm dừng mất nhiều công sức, nhất là khi lịch trình có nhiều hoạt động. Các công cụ AI cũng có thể đưa ra gợi ý không phù hợp với tuyến đường hoặc dữ liệu địa điểm thực tế.

**Giải pháp đề xuất**

- **POI Discovery:** Tìm kiếm địa điểm (Points of Interest) theo nhu cầu và danh mục hoạt động.
- **Route-Based POI Discovery:** Khám phá địa điểm dọc tuyến đường giữa điểm xuất phát và điểm đến.
- **Hybrid POI Intelligence và Ranking:** Chuẩn hóa, lọc trùng và xếp hạng địa điểm theo mức độ phù hợp.
- **Itinerary Planning:** Thêm, xóa, sắp xếp các điểm dừng và tính toán lại tuyến đường.
- **Route Optimization:** Tối ưu thứ tự điểm dừng, giữ nguyên điểm xuất phát và điểm đến.
- **Time & Budget Planning:** Kiểm tra thời gian, ngân sách và phát hiện xung đột trong lịch trình.
- **AI Itinerary Refinement:** Đề xuất điều chỉnh lịch trình dựa trên các địa điểm ứng viên của hệ thống.

**Lợi ích**

CoupleLife AI giúp tập trung các thao tác tìm kiếm, so sánh và lập kế hoạch vào một giao diện. Người dùng có thể lựa chọn địa điểm theo sở thích, xem tuyến đường và điều chỉnh lịch trình mà không phải tính toán lại từng điểm dừng bằng tay. Kiến trúc phân tách các thành phần giúp nhóm dễ bảo trì và mở rộng chức năng sau này.

### 3. Kiến trúc giải pháp

**Kiến trúc ứng dụng**

Frontend tiếp nhận thông tin từ người dùng và gửi yêu cầu đến Backend Gateway. Backend xử lý nghiệp vụ, xác thực, dữ liệu tài khoản và lịch trình, đồng thời gọi AI Service qua mạng Docker nội bộ. AI Service hỗ trợ xử lý dữ liệu POI, xếp hạng địa điểm và tinh chỉnh lịch trình. Dữ liệu ứng dụng được lưu trong PostgreSQL.

Hệ thống sử dụng dữ liệu địa điểm từ OpenStreetMap (OSM) và nguồn dữ liệu nội bộ, OSRM để định tuyến, Groq API cho mô hình ngôn ngữ, Cloudflare Workers AI (BGE-M3) cho embedding và Gmail SMTP để gửi email OTP.

**Kiến trúc AWS**

Người dùng truy cập website qua HTTPS tại Amazon CloudFront, với AWS WAF bảo vệ lớp biên. CloudFront phục vụ nội dung tĩnh từ S3 private thông qua Origin Access Control (OAC) và chuyển yêu cầu API đến Application Load Balancer (ALB). ALB phân phối yêu cầu đến Backend trên hai EC2 thuộc Auto Scaling Group. Mỗi EC2 chạy Backend và AI Service dưới dạng Docker containers.

VPC được chia thành sáu subnet trên hai Availability Zones tại Singapore. Hai NAT Gateway cung cấp kết nối ra Internet cho các máy chủ trong private app subnets. Cả hai Backend truy cập RDS PostgreSQL qua cùng một endpoint; cơ sở dữ liệu standby được đồng bộ để phục vụ failover. Website sử dụng tên miền mặc định của CloudFront. Kết nối từ CloudFront đến ALB sử dụng HTTP.

**Các dịch vụ AWS sử dụng**

| Dịch vụ | Vai trò |
|---|---|
| Amazon VPC, NAT Gateway, Internet Gateway, S3 Gateway Endpoint | Phân tách mạng và quản lý kết nối giữa các tài nguyên. |
| Amazon CloudFront, AWS WAF, Amazon S3 | Phân phối giao diện, bảo vệ lớp biên và lưu trữ nội dung tĩnh. |
| Application Load Balancer, Amazon EC2, Auto Scaling Group | Phân phối tải và duy trì các máy chủ ứng dụng trên hai AZ. |
| Amazon RDS PostgreSQL Multi-AZ | Lưu trữ dữ liệu và hỗ trợ chuyển đổi dự phòng. |
| Amazon ECR | Lưu trữ Docker images của Backend và AI Service. |
| AWS IAM, Secrets Manager, Systems Manager | Quản lý quyền, thông tin xác thực và triển khai trên EC2. |
| Amazon CloudWatch, Amazon SNS, AWS CloudTrail Event History | Giám sát tài nguyên, gửi cảnh báo và tra cứu hoạt động quản trị. |
| AWS Budgets, Cost Explorer | Theo dõi ngân sách và chi phí sử dụng. |

GitHub Actions xác thực với AWS thông qua IAM OIDC để chạy CI/CD. Pipeline kiểm thử ứng dụng, đẩy Docker images lên ECR, cập nhật S3 và CloudFront, thực hiện migration và cập nhật lần lượt các EC2 thông qua Systems Manager. Health check và rollback giúp hạn chế gián đoạn khi phát hành phiên bản mới.

**AWS Well-Architected Framework**

| Trụ cột | Lựa chọn thiết kế |
|---|---|
| Operational Excellence | Tự động hóa CI/CD, giám sát bằng CloudWatch và cập nhật lần lượt các máy chủ. |
| Security | Phân tách private subnets, WAF, S3 OAC, IAM OIDC, Secrets Manager và HTTPS tại CloudFront. |
| Reliability | Hai AZ, ALB health checks, Auto Scaling Group và RDS Multi-AZ. |
| Performance Efficiency | CloudFront CDN, phân phối tải qua ALB và sử dụng API AI bên ngoài. |
| Cost Optimization | Dự toán ngân sách, AWS Budgets, S3 Gateway Endpoint và dọn dẹp tài nguyên. |
| Sustainability | Tận dụng EC2 cho cả hai container, lựa chọn cấu hình theo nhu cầu và giải phóng tài nguyên không sử dụng. |

Tham khảo [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html).

### 4. Triển khai kỹ thuật

**Các giai đoạn triển khai**

Nhóm phát triển ứng dụng theo từng giai đoạn, bắt đầu từ nền tảng Backend, dữ liệu địa điểm và định tuyến, sau đó hoàn thiện xếp hạng và tối ưu lịch trình.

**Phase 1 – Backend Safety & Configuration**

- **1.1 – Test Database Isolation:** Đảm bảo môi trường kiểm thử cơ sở dữ liệu được tách biệt.
- **1.2 – Production SECRET_KEY:** Chuẩn hóa cấu hình SECRET_KEY cho môi trường production.
- **1.3 – AI Configuration:** Chuẩn hóa cấu hình kết nối và quản lý AI Provider.

**Phase 2 – Routing & Application Integration**

- **2.1 – POI & Google Maps Investigation:** Kiểm tra dữ liệu POI và quy trình tích hợp Google Maps.
- **2.2 – Fix POI Data Integrity:** Xử lý các vấn đề về tính toàn vẹn dữ liệu địa điểm.
- **2.3a – Google Maps Navigation Accuracy:** Cải thiện độ chính xác khi tạo liên kết điều hướng.
- **2.3b – Routing Service A → B:** Xây dựng dịch vụ định tuyến giữa điểm xuất phát và điểm đến.
- **2.4 – Chuẩn hóa tọa độ A/B:** Chuẩn hóa trạng thái và tọa độ của hai địa điểm đầu cuối trên Frontend.
- **2.5 – Kết nối Planner A/B với Routing Service:** Kết nối giao diện lập kế hoạch với Routing API.
- **2.6 – Route-Based POI Discovery:** Xây dựng chức năng khám phá POI dọc theo tuyến đường.

**Task 2.8 – Route-Based Itinerary Planning**

- **2.8.3 – Routing Engine:** Xây dựng và tích hợp bộ máy định tuyến.
- **2.8.4 – Route-Based POI Discovery:** Tìm kiếm địa điểm theo hành lang tuyến đường.
- **2.8.5 – Frontend API Integration:** Kết nối Frontend với API khám phá và định tuyến.
- **2.8.6 – Ranked POI Results UI:** Xây dựng giao diện hiển thị danh sách POI đã được xếp hạng.
- **2.8.7 – POI Selection & Stop Management:** Quản lý việc lựa chọn, thêm và xóa các điểm dừng.
- **2.8.8 – Itinerary Construction:** Xây dựng lịch trình từ điểm A qua các POI đã chọn đến điểm B.
- **2.8.9 – Multi-Waypoint Routing:** Tích hợp định tuyến qua nhiều điểm dừng.
- **2.8.10 – Route Optimization:** Tối ưu thứ tự các điểm dừng.
- **2.8.11 – Time & Budget Planning:** Kiểm tra thời gian và ngân sách của lịch trình.
- **2.8.12 – AI Itinerary Refinement:** Tích hợp AI để đề xuất tinh chỉnh lịch trình.

**Phase 3 – Route-Based POI Discovery Foundation**

- **3.1–3.10 – Route-Based POI Discovery Implementation:** Xây dựng và hoàn thiện các thành phần khám phá POI theo tuyến đường.
- **3.11 – Route POI Discovery Audit:** Kiểm tra các vấn đề về lọc danh mục và xử lý trùng lặp.
- **3.12 – Route POI Discovery Corrections:** Sửa lỗi chuẩn hóa danh mục và xử lý trùng lặp POI.
- **3.13 – Top 50 POI Selection Audit:** Kiểm tra quy tắc lựa chọn và giới hạn số lượng địa điểm ứng viên.

Các công việc Frontend và tích hợp liên quan bao gồm:

- Route Location Input.
- Route State & Coordinate Management.
- Routing API Integration.
- Route Map Display.
- Route POI Results Display.
- POI Marker & Card Synchronization.
- Add/Remove POI from Itinerary.
- Route Stops Management.
- Multi-Waypoint Route Recalculation.
- Origin/Destination Change Handling.
- Stale Request Protection.

**Phase 4 – Google Places Identity Resolution**

- **4.1 – Architecture Audit:** Kiểm tra kiến trúc định danh địa điểm hiện tại.
- **4.2 – API & Identity Specification:** Xây dựng đặc tả tích hợp Google Places API và dữ liệu định danh.
- **4.3 – Minimal Google Places Identity Resolution Implementation:** Tích hợp Google Places phía server, tìm kiếm địa điểm và xử lý matching.
- **4.4 – Verification & Closure:** Kiểm thử và hoàn thiện tích hợp định danh địa điểm.

**Phase 5 – Hybrid POI Intelligence & Ranking**

- **5.1 – POI Intelligence Architecture Audit:** Kiểm tra kiến trúc xử lý và xếp hạng POI.
- **5.2 – Category Canonicalization & Intent Relevance:** Chuẩn hóa danh mục và xác định mức độ phù hợp với mục đích chuyến đi.
- **5.3 – Scheduler-Owned Budget & Opening Hours:** Xử lý kiểm tra ngân sách và giờ hoạt động trong bước lập lịch trình.
- **5.4 – Ranking-to-Itinerary Regression:** Kiểm thử hồi quy luồng xếp hạng, lựa chọn POI và xây dựng lịch trình.

**Phase 6 – Itinerary Optimization**

- **6.1 – Itinerary Optimization Foundation:** Xây dựng nền tảng tối ưu hóa lịch trình.
- Selected Stop Ordering: Xác định thứ tự các điểm dừng.
- Manual Stop Ordering: Cho phép người dùng tự sắp xếp điểm dừng.
- Drag-and-Drop Reordering: Hỗ trợ kéo thả để thay đổi thứ tự.
- Keyboard Reordering: Hỗ trợ thay đổi thứ tự bằng bàn phím.
- Origin & Destination Preservation: Giữ nguyên điểm xuất phát và điểm đến.
- Intermediate Stop Optimization: Tối ưu các điểm dừng trung gian.
- Route Progress Ordering: Sắp xếp theo tiến trình tuyến đường.
- Two-Opt Optimization: Áp dụng thuật toán tối ưu thứ tự điểm dừng.
- Multi-Waypoint Routing Integration: Tích hợp định tuyến nhiều điểm.
- Itinerary Schedule Validation: Kiểm tra tính hợp lệ của lịch trình.
- Conflict Detection: Phát hiện xung đột lịch trình.
- Conflict Resolution Proposals: Đề xuất phương án xử lý xung đột.
- Accept/Reject Proposals: Cho phép người dùng chấp nhận hoặc từ chối đề xuất.
- Stale Revision Protection: Ngăn áp dụng các thay đổi dựa trên phiên bản lịch trình cũ.
- Route & Map Synchronization: Đồng bộ thứ tự điểm dừng, tuyến đường và bản đồ.
- Itinerary UI Integration: Tích hợp các chức năng quản lý lịch trình trên giao diện.

**Giai đoạn hoàn thiện và triển khai AWS**

Sau Phase 1–6, nhóm tiếp tục các công việc:

- Final Validation & Release Gate: Kiểm thử các luồng chính, lỗi đầu vào, lỗi provider, regression và build.
- Security Hardening: Hoàn thiện cấu hình production, quản lý secrets và xử lý log an toàn.
- Authentication Foundation: Hoàn thiện xác thực và quản lý phiên đăng nhập phía Backend.
- Authentication & Data Layer: Tích hợp cơ chế JWT/session của Backend với PostgreSQL.
- AWS Deployment: Đóng gói Docker, thiết lập mạng, cơ sở dữ liệu, EC2 và các dịch vụ hỗ trợ.
- CI/CD & Validation: Tự động hóa kiểm thử, migration, rolling deployment và kiểm tra ứng dụng trên AWS; tích hợp chức năng quên mật khẩu bằng email OTP.

**Yêu cầu kỹ thuật**

- **Frontend:** React, Vite, TypeScript, quản lý trạng thái và tích hợp API.
- **Backend:** Python, FastAPI, Pydantic, REST API, JWT/session và xác thực nội bộ.
- **AI Service:** Python, FastAPI, xử lý dữ liệu POI, ranking và AI itinerary refinement.
- **POI Data:** OpenStreetMap, Overpass API trong giai đoạn phát triển và dữ liệu địa điểm nội bộ.
- **Routing:** OSRM, GeoJSON và tọa độ địa lý.
- **Place Identity:** Place ID và cơ chế matching trong giai đoạn phát triển định danh địa điểm.
- **AI Integration:** Groq API và Cloudflare Workers AI (BGE-M3).
- **Email:** Gmail SMTP phục vụ khôi phục mật khẩu bằng OTP.
- **Storage:** PostgreSQL, Alembic migration; Amazon RDS cho môi trường AWS.
- **Deployment:** Docker, EC2, Auto Scaling Group, ECR, S3, CloudFront, Systems Manager, Secrets Manager và GitHub Actions.

### 5. Lộ trình & Mốc triển khai

Nhóm hoàn thiện sản phẩm trong môi trường local trước, sau đó tích hợp và triển khai trên AWS.

**Giai đoạn phát triển nền tảng**

- **Phase 1–3:** Hoàn thiện nền tảng Backend, dữ liệu POI, routing, khám phá địa điểm theo tuyến đường và các luồng Frontend liên quan.
- **Phase 4:** Tích hợp Google Places Identity Resolution trong quá trình phát triển.
- **Phase 5:** Hoàn thiện Hybrid POI Intelligence và Ranking.
- **Phase 6:** Hoàn thiện Itinerary Optimization và các chức năng quản lý lịch trình.

**Giai đoạn kiểm thử và bảo mật**

- Thực hiện Final Validation & Release Gate.
- Kiểm thử tìm kiếm POI, định tuyến, lựa chọn điểm dừng và tối ưu lịch trình.
- Kiểm tra lỗi dữ liệu, lỗi kết nối và lỗi từ nhà cung cấp dịch vụ.
- Hoàn thiện bảo mật và cấu hình production.

**Giai đoạn tích hợp AWS**

- **Bước 1 – Authentication Foundation:** Hoàn thiện xác thực và quản lý phiên đăng nhập.
- **Bước 2 – Authentication Integration:** Kết nối cơ chế xác thực của Backend với Frontend.
- **Bước 3 – Data Layer:** Chuẩn bị PostgreSQL, migration và dữ liệu ứng dụng.
- **Bước 4 – Local Integration Testing:** Kiểm thử các chức năng với cấu hình local.
- **Bước 5 – AWS Infrastructure:** Thiết lập mạng, cơ sở dữ liệu, EC2, container, phân phối giao diện và quản lý secrets.
- **Bước 6 – Deployment & Validation:** Triển khai lên AWS, hoàn thiện CI/CD, kiểm tra hoạt động thực tế và giám sát chi phí.

**Giai đoạn vận hành:** Duy trì hệ thống trong 14 ngày, theo dõi tình trạng ứng dụng và chi phí, sau đó sao lưu dữ liệu cần thiết và dọn dẹp tài nguyên.

### 6. Ước tính ngân sách

Dự toán được lập bằng AWS Pricing Calculator tại Region Singapore, với hai EC2 `t3.small` (20 GiB gp3 mỗi máy), RDS PostgreSQL `db.t3.micro` Multi-AZ (20 GiB gp3), hai NAT Gateway và một ALB. Thời gian hoạt động dự kiến là 730 giờ/tháng.

| Dịch vụ | Chi phí dự kiến (USD/tháng) |
|---|---:|
| VPC, NAT Gateway và public IPv4 | 101,32 |
| Amazon RDS PostgreSQL | 46,40 |
| Amazon EC2 và EBS | 42,38 |
| Application Load Balancer | 24,24 |
| AWS WAF | 7,60 |
| AWS Secrets Manager | 1,70 |
| Amazon ECR | 0,10 |
| Amazon S3 | 0,03 |
| Amazon SNS | 0,00 |
| Amazon CloudFront | 0,00 |
| **Tổng cộng** | **223,77** |

[Dự toán CoupleLife AI trên AWS Pricing Calculator](https://calculator.aws/#/estimate?id=01ec0aee30504f4a008d08d0db765ffb13d06485).

| Hạng mục | Số tiền (USD) |
|---|---:|
| Chi phí dự kiến trong 14 ngày (336 giờ) | 103,00 |
| Ngân sách nội bộ | 120,00 |
| Dự phòng | 17,00 |

Nhóm dự kiến sử dụng AWS Promotional Credits với hạn mức 200 USD theo điều kiện của tài khoản. Chi phí trên được ước tính trước credits và thuế, dựa trên cấu hình và lưu lượng giả định. Chi phí thực tế có thể thay đổi theo thời gian hoạt động, lưu lượng mạng, API requests và mức sử dụng các dịch vụ giám sát.

**Phương án tối ưu chi phí**

- Sử dụng CloudFront để cache nội dung tĩnh và S3 Gateway Endpoint để giảm lưu lượng S3 qua NAT Gateway.
- Chạy Backend và AI Service trên cùng mỗi EC2, sử dụng API AI bên ngoài trong hạn mức miễn phí thay vì máy chủ GPU.
- Giữ hai NAT Gateway và RDS Multi-AZ để duy trì tính sẵn sàng của hệ thống.
- Theo dõi Cost Explorer, Bills và số dư Credits; đặt cảnh báo AWS Budgets tại 50%, 80% và 100% ngân sách.
- Dọn dẹp tài nguyên khi kết thúc thời gian vận hành để tránh phát sinh chi phí.

### 7. Đánh giá rủi ro

| Rủi ro | Ảnh hưởng | Khả năng | Phương án giảm thiểu |
|---|---|---|---|
| Dữ liệu POI thiếu, sai hoặc trùng lặp | Cao | Trung bình | Chuẩn hóa, lọc trùng và kiểm tra dữ liệu địa điểm. |
| Dịch vụ định tuyến hoặc AI bên ngoài gặp lỗi, vượt quota | Cao | Trung bình | Giới hạn request và thời gian chờ; sử dụng dữ liệu sẵn có hoặc fallback khi có thể. |
| Lịch trình vượt ngân sách hoặc xung đột thời gian | Trung bình | Trung bình | Kiểm tra ràng buộc trước khi áp dụng đề xuất. |
| Lộ thông tin xác thực hoặc truy cập trái phép | Cao | Trung bình | Secrets Manager, IAM giới hạn quyền, xác thực Backend và bảo vệ phiên đăng nhập. |
| Kết nối origin ALB qua HTTP | Cao | Trung bình | Giới hạn truy cập origin; xem xét HTTPS cho kết nối CloudFront đến ALB khi mở rộng hệ thống. |
| Máy chủ hoặc cơ sở dữ liệu gặp sự cố | Cao | Thấp đến trung bình | Hai AZ, ALB health checks, ASG, RDS Multi-AZ và backup. |
| Lỗi triển khai hoặc migration | Cao | Trung bình | Kiểm thử, kiểm tra tương thích schema, rolling deployment và rollback image. |
| Cảnh báo không đến người nhận | Trung bình | Trung bình | Xác nhận SNS email subscription và kiểm tra việc nhận cảnh báo. |
| Vượt ngân sách AWS | Cao | Trung bình | Cảnh báo ngân sách, theo dõi chi phí hằng ngày và dọn dẹp tài nguyên đúng hạn. |

**Kế hoạch dự phòng**

Khi dịch vụ bên ngoài gián đoạn, hệ thống thông báo lỗi và sử dụng cơ chế fallback đối với chức năng có hỗ trợ. Khi phiên bản mới gặp lỗi, khôi phục Docker image trước đó sau khi kiểm tra tính tương thích với cơ sở dữ liệu. Nếu RDS gặp sự cố, sử dụng cơ chế failover hoặc khôi phục từ backup. Khi chi phí có nguy cơ vượt ngân sách, nhóm rà soát mức sử dụng, dừng tài nguyên không cần thiết và sao lưu dữ liệu trước khi dọn dẹp.

### 8. Kết quả kỳ vọng

**Kết quả kỹ thuật**

- Hoàn thiện ứng dụng web hỗ trợ khám phá địa điểm, định tuyến nhiều điểm và lập lịch trình theo sở thích, thời gian và ngân sách.
- Sử dụng dữ liệu địa điểm thực tế để xếp hạng và đề xuất các điểm dừng phù hợp.
- Triển khai ứng dụng trên AWS với hai EC2 ở hai Availability Zones và RDS PostgreSQL Multi-AZ.
- Hoàn thiện CI/CD, kiểm tra sức khỏe ứng dụng, xác thực tài khoản và khôi phục mật khẩu bằng email OTP.
- Thiết lập giám sát tài nguyên, cảnh báo ngân sách và quy trình dọn dẹp sau thời gian vận hành.

**Giá trị dài hạn**

CoupleLife AI tạo nền tảng để phát triển thêm các chức năng cá nhân hóa, lưu lịch sử chuyến đi và mở rộng dữ liệu địa điểm sang những khu vực khác. Kiến trúc phân tách giao diện, nghiệp vụ và AI giúp việc bảo trì và mở rộng hệ thống thuận tiện hơn.
