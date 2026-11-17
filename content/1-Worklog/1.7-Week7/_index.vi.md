
---
title: "Worklog Tuần 7"
date: 2026-10-26
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

- Tìm hiểu mô hình Serverless và vai trò của AWS Lambda trong việc thực thi code mà không cần tự quản lý máy chủ.
- Làm quen với Lambda Function, Handler, Event, Trigger và IAM Execution Role.
- Hiểu những trường hợp nên sử dụng Lambda, cũng như một số giới hạn cơ bản của dịch vụ.
- Tìm hiểu Amazon API Gateway, phân biệt sơ lược HTTP API và REST API.
- Phân tích cách kết hợp API Gateway với Lambda để xử lý một API đơn giản, đồng thời chú ý quyền truy cập và chi phí sử dụng.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | Tìm hiểu Serverless và AWS Lambda. So sánh cách chạy ứng dụng trên EC2 với Lambda, xem những trường hợp sử dụng như xử lý API hoặc phản ứng với sự kiện từ dịch vụ AWS khác. | 26/10/2026 | 26/10/2026 | [What Is AWS Lambda?](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| 3 | Tìm hiểu Lambda Function và cấu trúc Python Handler `lambda_handler(event, context)`. Đọc code mẫu, xác định dữ liệu đầu vào `event` và kết quả trả về; thử phác thảo một ví dụ xử lý dữ liệu đơn giản trên máy cá nhân. | 27/10/2026 | 27/10/2026 | [Lambda Python Handler](https://docs.aws.amazon.com/lambda/latest/dg/python-handler.html) |
| 4 | Tìm hiểu Lambda Trigger, IAM Execution Role và cách Lambda ghi log qua CloudWatch Logs. Đọc thêm về Timeout, Memory, Cold Start và cách tính phí Lambda; chỉ xem hướng dẫn, không tạo Function hoặc cấu hình Trigger thực tế. | 28/10/2026 | 28/10/2026 | [Invoking Lambda with Events](https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html), [Lambda Execution Role](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html), [Lambda Pricing](https://aws.amazon.com/lambda/pricing/) |
| 5 | Tìm hiểu Amazon API Gateway, mục đích sử dụng và các khái niệm Route, HTTP Method, Endpoint. So sánh cơ bản HTTP API với REST API và xem ví dụ Route `GET /hello`. | 29/10/2026 | 29/10/2026 | [API Gateway HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api.html), [HTTP APIs vs REST APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vs-rest.html) |
| 6 | Phân tích mô hình kết nối API Gateway HTTP API với Lambda thông qua Lambda Proxy Integration. Xem cấu trúc Request Event và Response, mô phỏng luồng `GET /hello` trả về HTTP 200 cùng nội dung JSON mà không triển khai API lên AWS. | 30/10/2026 | 30/10/2026 | [Lambda Proxy Integration for HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-develop-integrations-lambda.html) |
| 7 | Ôn tập và vẽ sơ đồ `Client → API Gateway → Lambda → Response` bằng draw.io. Tìm hiểu sơ lược IAM, JWT Authorizer (có thể dùng Amazon Cognito) và Lambda Authorizer trong việc bảo vệ API; xem bảng giá API Gateway và Lambda để tránh sử dụng vượt hạn mức. | 31/10/2026 | 31/10/2026 | [HTTP API Access Control](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-access-control.html), [API Gateway Pricing](https://aws.amazon.com/api-gateway/pricing/), [Lambda Pricing](https://aws.amazon.com/lambda/pricing/) |

### Kết quả đạt được tuần 7:

**Kiến thức đã tìm hiểu:**

- Hiểu Serverless không có nghĩa là không sử dụng máy chủ, mà là AWS quản lý phần hạ tầng để người phát triển tập trung vào code. Nhận thấy Lambda phù hợp với những tác vụ xử lý ngắn, chạy theo sự kiện hoặc xử lý request từ API.
- Biết Lambda Function có Handler làm điểm bắt đầu xử lý. Với Python, Handler thường nhận hai tham số `event` và `context`; dữ liệu trong `event` thay đổi tùy theo nguồn gọi Function.
- Nắm được vai trò của Trigger trong việc khởi chạy Lambda và IAM Execution Role trong việc cấp quyền để Function truy cập các dịch vụ AWS khác, chẳng hạn ghi log vào CloudWatch Logs.
- Biết Lambda có giới hạn về thời gian chạy, bộ nhớ và có thể gặp Cold Start. Hiểu chi phí Lambda phụ thuộc vào số lần gọi, thời lượng và cấu hình sử dụng, không nên mặc định mọi lượt chạy đều miễn phí.
- Hiểu API Gateway là dịch vụ tiếp nhận và điều hướng API Request tới Backend. Làm quen với HTTP Method, Route, Endpoint; biết HTTP API thường đơn giản và chi phí thấp hơn REST API, trong khi REST API có thêm các tính năng quản lý nâng cao.
- Hình dung được luồng `Client → API Gateway → Lambda → API Gateway → Client` và vai trò của Lambda Proxy Integration khi trả dữ liệu cho client.
- Biết API có thể được bảo vệ bằng các cơ chế như IAM, JWT Authorizer (có thể dùng Cognito) hoặc Lambda Authorizer; mới tìm hiểu ở mức tổng quan, chưa cấu hình xác thực thực tế.

**Tìm hiểu và luyện tập theo tài liệu:**

- Đọc ví dụ Python Handler và ghi chú ý nghĩa của `event`, `context`, `statusCode` và `body` trong các ví dụ phù hợp với kiểu gọi API.
- Phác thảo tình huống `GET /hello` nhận request và trả về JSON như `{"message": "Hello"}` để hiểu đường đi của dữ liệu, không cần tạo API Endpoint thật.
- Sử dụng draw.io để minh họa mối liên hệ giữa Client, API Gateway và Lambda; ôn lại kiến thức về Backend API và HTTP Response.
- So sánh Lambda với EC2 ở mức cơ bản, tập trung vào việc quản lý máy chủ, cách thực thi code và tình huống sử dụng.
- Tham khảo bảng giá chính thức của Lambda và API Gateway. Tuần này chỉ đọc tài liệu, mô phỏng dữ liệu và phân tích sơ đồ; không triển khai Lambda Function, API Gateway hay tài nguyên liên quan trên AWS để tránh phát sinh chi phí không cần thiết.

**Khó khăn gặp phải và cách giải quyết:**

- Phần mất nhiều thời gian tìm hiểu là cách Lambda nhận dữ liệu qua `event`. Khi đối chiếu các ví dụ, nhận thấy cấu trúc `event` phụ thuộc vào nguồn kích hoạt. Việc bắt đầu từ một JSON mẫu đơn giản và theo dõi dữ liệu đi qua Handler giúp cách hoạt động trở nên dễ hình dung hơn.
- Khi xem hướng dẫn kết nối API Gateway với Lambda, một câu hỏi đặt ra là request được chuyển tiếp như thế nào và ai chịu trách nhiệm tạo HTTP Response. Tôi đã xem lại ví dụ Lambda Proxy Integration, tách quá trình thành các bước nhận request, gọi Function và trả kết quả để hiểu rõ trách nhiệm của từng dịch vụ.
