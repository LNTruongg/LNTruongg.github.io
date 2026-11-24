---
title: "Week 7 Worklog"
date: 2026-10-26
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

- Understand the Serverless model and the role of AWS Lambda in running code without managing servers.
- Become familiar with Lambda Functions, Handlers, Events, Triggers, and IAM Execution Roles.
- Learn about common Lambda use cases and some of the service's basic limitations.
- Explore Amazon API Gateway and understand the basic differences between HTTP APIs and REST APIs.
- Analyze how API Gateway can be integrated with Lambda to handle a simple API while considering access control and usage costs.
- Continue exploring the LoveSpot project, focusing on how the Frontend, Backend, and recommendation system exchange data through APIs.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about Serverless computing and AWS Lambda. Compare running applications on EC2 with using Lambda, and explore use cases such as handling API requests or responding to events from other AWS services. | 2026-10-26 | 2026-10-26 | [What Is AWS Lambda?](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| 3 | Explore Lambda Functions and the Python Handler structure `lambda_handler(event, context)`. Read sample code, identify the input `event` and returned results, and outline a simple data-processing example on a local computer. | 2026-10-27 | 2026-10-27 | [Lambda Python Handler](https://docs.aws.amazon.com/lambda/latest/dg/python-handler.html) |
| 4 | Learn about Lambda Triggers, IAM Execution Roles, and how Lambda writes logs to CloudWatch Logs. Study Timeout, Memory, Cold Starts, and Lambda pricing without creating actual Functions or configuring Triggers. | 2026-10-28 | 2026-10-28 | [Invoking Lambda with Events](https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html), [Lambda Execution Role](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html), [Lambda Pricing](https://aws.amazon.com/lambda/pricing/) |
| 5 | Explore Amazon API Gateway, its purpose, and concepts such as Routes, HTTP Methods, and Endpoints. Compare HTTP APIs with REST APIs and review an example route, `GET /hello`. | 2026-10-29 | 2026-10-29 | [API Gateway HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api.html), [HTTP APIs vs REST APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vs-rest.html) |
| 6 | Analyze how API Gateway HTTP APIs integrate with Lambda through Lambda Proxy Integration. Study Request Events and Responses, and simulate a `GET /hello` request returning HTTP 200 with a JSON response without deploying an API to AWS. **Project Work:** Explore how the LoveSpot Frontend sends requests to the Backend and how venue recommendations can be returned as JSON data. | 2026-10-30 | 2026-10-30 | [Lambda Proxy Integration for HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-develop-integrations-lambda.html), [ASP.NET Core Web API](https://learn.microsoft.com/en-us/aspnet/core/web-api/) |
| 7 | Review the week's topics and create a `Client → API Gateway → Lambda → Response` diagram using draw.io. Learn about IAM authorization, JWT Authorizers (which can use Amazon Cognito), and Lambda Authorizers for securing APIs. Review API Gateway and Lambda pricing to avoid exceeding usage limits. | 2026-10-31 | 2026-10-31 | [HTTP API Access Control](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-access-control.html), [API Gateway Pricing](https://aws.amazon.com/api-gateway/pricing/), [Lambda Pricing](https://aws.amazon.com/lambda/pricing/) |

### Week 7 Results:

**Knowledge Gained:**

- Understood that Serverless does not mean servers are absent. Instead, AWS manages the underlying infrastructure so developers can focus on writing code. Learned that Lambda is suitable for short-running tasks, event-driven processing, and handling API requests.
- Learned that a Lambda Function uses a Handler as its entry point. In Python, the Handler usually receives two parameters, `event` and `context`, and the structure of `event` depends on the invocation source.
- Understood the role of Triggers in invoking Lambda and IAM Execution Roles in granting Functions permission to access other AWS services, such as writing logs to CloudWatch Logs.
- Learned that Lambda has execution time and memory limits and may experience Cold Starts. Understood that Lambda costs depend on request volume, execution duration, and resource configuration, so not every invocation should be assumed to be free.
- Understood that API Gateway receives API requests and routes them to Backend services. Became familiar with HTTP Methods, Routes, and Endpoints. Learned that HTTP APIs are generally simpler and less expensive than REST APIs, while REST APIs provide additional API management features.
- Understood the basic request flow `Client → API Gateway → Lambda → API Gateway → Client` and how Lambda Proxy Integration allows Lambda responses to be returned to clients.
- Learned that APIs can be protected using IAM authorization, JWT Authorizers (which can integrate with Amazon Cognito), or Lambda Authorizers. These concepts were studied at an introductory level without configuring actual authentication services.

**Learning Activities and Practice:**

- Read Python Handler examples and studied the meanings of `event`, `context`, `statusCode`, and `body` in examples relevant to API requests.
- Outlined a simple `GET /hello` scenario that receives a request and returns a JSON response such as `{"message": "Hello"}`, without creating a real API Endpoint.
- Used draw.io to illustrate the relationship between Clients, API Gateway, and Lambda while reviewing Backend API and HTTP Response concepts.
- Compared Lambda with EC2, focusing on server management, code execution, and suitable use cases.
- Reviewed official AWS pricing information for Lambda and API Gateway. This week's activities were limited to documentation, data simulations, and architecture analysis. No Lambda Functions, API Gateway APIs, or related AWS resources were deployed to avoid unnecessary costs.

**LoveSpot Project Activities:**

- Continued exploring how LoveSpot components exchange information, including the React/Vite Frontend, ASP.NET Core Backend, and venue recommendation system.
- Outlined a basic request-processing workflow: users enter their preferences through the interface, the Frontend sends requests to the Backend, and the returned results are displayed as recommended places.
- Studied how API Requests and Responses could be organized using JSON and identified several potential API operations for searching for venues and generating itineraries.
- Connected the API Gateway and Lambda concepts learned during the week with API-based communication. These activities focused on understanding and designing data flows; API Gateway and Lambda had not been deployed for LoveSpot on AWS at this stage.

**Challenges Encountered and Solutions:**

- One of the more challenging topics was understanding how Lambda receives information through `event`. After comparing different examples, I realized that the event structure depends on the invocation source. Starting with a simple JSON example and tracing the data through the Handler made the process easier to understand.
- When studying API Gateway integration with Lambda, I initially had questions about how requests are forwarded and which component is responsible for creating the HTTP Response. Reviewing Lambda Proxy Integration examples and breaking the process into receiving the request, invoking the Function, and returning the response helped me understand each service's responsibilities.