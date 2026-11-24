
---
title: "Các bài blog đã đăng"
date: 2026-11-17
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Trong quá trình học tập và tìm hiểu về Amazon Web Services (AWS), tôi đã thực hiện và chia sẻ các bài viết phân tích những tình huống kỹ thuật có thể gặp phải khi xây dựng, vận hành và bảo mật hệ thống trên nền tảng Cloud.

Dưới đây là ba bài blog tôi đã đăng, tập trung vào cách hoạt động của các dịch vụ AWS, những vấn đề dễ bị bỏ sót và các giải pháp khắc phục.

### [Blog 1 - AWS LAMBDA + SQS: VÌ SAO MỘT MESSAGE LỖI CÓ THỂ KHIẾN CẢ BATCH BỊ XỬ LÝ LẠI?](3.1-Blog1/)

Bài viết phân tích cơ chế xử lý message theo batch khi kết hợp AWS Lambda với Amazon SQS. Nếu một message xử lý thất bại, toàn bộ batch có thể bị xử lý lại theo cơ chế mặc định, dẫn đến việc xử lý trùng lặp các message đã thành công.

Bài viết đồng thời giới thiệu **Partial Batch Response**, **Idempotency** và những lưu ý giúp xây dựng hệ thống xử lý message đáng tin cậy hơn.

**[Xem bài viết gốc trên Facebook](https://www.facebook.com/share/p/1C8K1bvGzK/)**

### [Blog 2 - AMAZON S3: VÌ SAO XÓA FILE RỒI VẪN CÓ THỂ PHÁT SINH CHI PHÍ LƯU TRỮ?](3.2-Blog2/)

Bài viết tìm hiểu cách **S3 Versioning** và **Lifecycle Rules** tương tác với nhau. Khi Versioning được bật, thao tác xóa object có thể chỉ tạo ra một Delete Marker, trong khi các phiên bản cũ vẫn được lưu trữ và tiếp tục phát sinh chi phí.

Thông qua đó, bài viết giải thích vai trò của **Delete Markers**, **Noncurrent Versions** và cách cấu hình Lifecycle phù hợp để quản lý dữ liệu và tối ưu chi phí lưu trữ trên Amazon S3.

**[Xem bài viết gốc trên Facebook](https://www.facebook.com/share/p/18Z3mD7KML/)**

### [Blog 3 - AWS API GATEWAY: VÌ SAO CACHE MỘT KẾT QUẢ ALLOW CÓ THỂ KHIẾN ROUTE KHÁC ĐƯỢC TRUY CẬP NGOÀI Ý MUỐN?](3.3-Blog3/)

Bài viết phân tích một rủi ro phân quyền khi sử dụng **Amazon API Gateway HTTP API** kết hợp **Lambda Authorizer**, **Simple Responses** và **Authorizer Caching**.

Nếu cache key chỉ dựa trên thông tin người dùng mà không phân biệt route, kết quả `Allow` từ một route có thể được tái sử dụng cho route khác ngoài ý muốn.

Bài viết giải thích nguyên nhân, cơ chế Authorizer Caching và các giải pháp như bổ sung `$context.routeKey` vào Identity Sources hoặc thiết kế chính sách phân quyền phù hợp.

**[Xem bài viết gốc trên Facebook](https://www.facebook.com/share/p/1BPEBPipns/)**
