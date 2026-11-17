
---
title: "Week 7 Worklog"
date: 2026-10-26
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

- Learn about the Serverless model and how AWS Lambda runs code without requiring users to manage servers.
- Become familiar with Lambda Functions, Handlers, Events, Triggers, and IAM Execution Roles.
- Understand common Lambda use cases and some basic service limitations.
- Explore Amazon API Gateway and the main differences between HTTP APIs and REST APIs.
- Analyze how API Gateway and Lambda work together to handle a simple API request, while considering access control and costs.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Serverless and AWS Lambda. Compare running an application on EC2 with using Lambda, and review common use cases such as API processing and responding to events from other AWS services. | 26/10/2026 | 26/10/2026 | [What Is AWS Lambda?](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| 3 | Learn about Lambda Functions and the Python Handler structure `lambda_handler(event, context)`. Read sample code, identify the input `event` and returned result, and sketch a simple data-processing example on a personal computer. | 27/10/2026 | 27/10/2026 | [Lambda Python Handler](https://docs.aws.amazon.com/lambda/latest/dg/python-handler.html) |
| 4 | Learn about Lambda Triggers, IAM Execution Roles, and how Lambda can write logs to CloudWatch Logs. Read about Timeout, Memory, Cold Starts, and Lambda pricing; review the guide without creating actual Functions or Triggers. | 28/10/2026 | 28/10/2026 | [Invoking Lambda with Events](https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html), [Lambda Execution Role](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html), [Lambda Pricing](https://aws.amazon.com/lambda/pricing/) |
| 5 | Learn about Amazon API Gateway, its purpose, and basic concepts such as Routes, HTTP Methods, and Endpoints. Compare HTTP APIs with REST APIs and review a sample `GET /hello` route. | 29/10/2026 | 29/10/2026 | [API Gateway HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api.html), [HTTP APIs vs REST APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vs-rest.html) |
| 6 | Analyze how an API Gateway HTTP API connects to Lambda using Lambda Proxy Integration. Review Request Event and Response formats, and model a `GET /hello` flow returning HTTP 200 with a JSON message without deploying the API on AWS. | 30/10/2026 | 30/10/2026 | [Lambda Proxy Integration for HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-develop-integrations-lambda.html) |
| 7 | Review the week's topics and draw a `Client → API Gateway → Lambda → Response` diagram using draw.io. Explore IAM, JWT Authorizers (including Amazon Cognito), and Lambda Authorizers at an introductory level, and check Lambda and API Gateway pricing to avoid unnecessary charges. | 31/10/2026 | 31/10/2026 | [HTTP API Access Control](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-access-control.html), [API Gateway Pricing](https://aws.amazon.com/api-gateway/pricing/), [Lambda Pricing](https://aws.amazon.com/lambda/pricing/) |

### Week 7 Achievements:

**Knowledge Gained:**

- Understood that Serverless does not mean servers are absent; instead, AWS manages the infrastructure so developers can focus on application code. Learned that Lambda is useful for short tasks, event-driven processing, and handling API requests.
- Learned that a Lambda Function uses a Handler as its entry point. In Python, the Handler usually receives `event` and `context`, while the structure of `event` depends on the service invoking the Function.
- Understood the role of Triggers in invoking Lambda and IAM Execution Roles in granting a Function permission to access AWS services, such as writing logs to CloudWatch Logs.
- Learned that Lambda has limits related to execution time and memory, and that Cold Starts can affect startup time. Understood that Lambda pricing depends on requests, execution duration, and resource settings, so not every invocation should be assumed to be free.
- Understood that API Gateway receives and routes API requests to a Backend. Became familiar with HTTP Methods, Routes, and Endpoints. Learned that HTTP APIs are generally simpler and less expensive than REST APIs, while REST APIs provide more advanced management features.
- Understood the basic flow `Client → API Gateway → Lambda → API Gateway → Client` and how Lambda Proxy Integration returns data to the client.
- Learned that APIs can use IAM, JWT Authorizers (including Cognito), or Lambda Authorizers for access control, but only studied these mechanisms at an introductory level without configuring authentication.

**Learning and Practice with the Materials:**

- Read a sample Python Handler and noted the meanings of `event`, `context`, `statusCode`, and `body` in examples relevant to API requests.
- Sketched a simple `GET /hello` example that receives a request and returns JSON such as `{"message": "Hello"}`, without creating a real API Endpoint.
- Used draw.io to illustrate how a Client, API Gateway, and Lambda connect, reinforcing basic Backend API and HTTP Response concepts.
- Compared Lambda and EC2 at a beginner level, focusing on server management, code execution, and suitable use cases.
- Reviewed official Lambda and API Gateway pricing. This week's work was limited to documentation, sample data, and diagrams; no Lambda Functions, API Gateways, or related AWS resources were deployed to avoid unnecessary costs.

**Challenges Encountered and Solutions:**

- One of the more time-consuming topics was understanding how Lambda receives information through `event`. Comparing examples showed that the `event` structure changes depending on the trigger. Starting with a small JSON example and tracing how it enters the Handler made the process easier to follow.
- While reading about API Gateway and Lambda integration, an important question was how the request is forwarded and which service prepares the HTTP Response. Reviewing the Lambda Proxy Integration example and breaking the flow into receiving the request, invoking the Function, and returning the result helped clarify each service's responsibility.
