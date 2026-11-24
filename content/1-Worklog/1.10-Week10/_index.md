---
title: "Worklog Week 10"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

- Learn the basic functions of Amazon CloudWatch and AWS CloudTrail for system monitoring and activity auditing.
- Understand the general purposes of AWS security services such as IAM Identity Center, KMS, Secrets Manager, GuardDuty, and WAF.
- **Project Work:** Continue developing an application that recommends restaurants and generates dining itineraries in Ho Chi Minh City.
- **Project Work:** Analyze user requirements, review restaurant data, and explore recommendation approaches.
- **Project Work:** Test common usage scenarios and identify areas for improvement.

### Tasks to Complete This Week:

| Day | Task | Start Date | Completion Date | References |
| --- | --- | --- | --- | --- |
| Monday | Learn about Amazon CloudWatch, including Metrics, Logs, and Alarms. Explore AWS CloudTrail and Event History to understand the difference between system monitoring and auditing activities within an AWS account. | 16/11/2026 | 16/11/2026 | [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html), [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html) |
| Tuesday | Study the basic purposes of IAM Identity Center, KMS, Secrets Manager, GuardDuty, and AWS WAF. Review security concepts, explore pricing, and identify services that may be useful when deploying the application to AWS in the future. | 17/11/2026 | 17/11/2026 | [AWS Security](https://aws.amazon.com/security/), [AWS Pricing](https://aws.amazon.com/pricing/) |
| Wednesday | **Project Work:** Review the goals and requirements of the restaurant recommendation and itinerary planning application for Ho Chi Minh City. Identify user inputs such as preferred area, budget, food preferences, available time, and desired number of locations. | 18/11/2026 | 18/11/2026 | Project requirements and source code |
| Thursday | **Project Work:** Review the restaurant dataset for Ho Chi Minh City, focusing on restaurant names, addresses, GPS coordinates, and review information. Explore data cleaning, identify invalid records, and prepare data for the recommendation system. | 19/11/2026 | 19/11/2026 | Project dataset and data processing documentation |
| Friday | **Project Work:** Analyze restaurant recommendation logic based on user preferences. Consider how to combine relevance, geographical distance, and restaurant information to select suitable locations and determine a reasonable itinerary order. | 20/11/2026 | 20/11/2026 | Project source code and recommendation system design documents |
| Saturday | **Project Work:** Test itinerary recommendations using different inputs, such as changes in budget, location, and food preferences. Review the results and identify issues that require further improvement. | 21/11/2026 | 21/11/2026 | Project source code, dataset, and test scenarios |

### Expected Outcomes for Week 10:

**AWS Knowledge Acquired:**

- Understand how Amazon CloudWatch supports system monitoring through Metrics, Logs, and Alarms.
- Distinguish between CloudWatch for system monitoring and CloudTrail for recording activities related to AWS accounts and resources.
- Understand the basic purposes of IAM Identity Center, KMS, Secrets Manager, GuardDuty, and WAF.
- Recognize the importance of cost management when selecting AWS services.

**Expected Project Outcomes:**

- **Project Work:** Identify the main requirements and features of the restaurant recommendation and itinerary planning application for Ho Chi Minh City.
- **Project Work:** Understand the structure and quality of restaurant data, particularly addresses and GPS coordinates.
- **Project Work:** Identify recommendation criteria such as food preferences, budget, location, and distance.
- **Project Work:** Develop or improve the proposed workflow from user input to restaurant selection and itinerary generation.
- **Project Work:** Prepare test scenarios to evaluate recommendation results.

**Challenges and Proposed Solutions:**

- **AWS Knowledge:** Continue learning from official documentation and avoid enabling potentially chargeable services unless necessary.
- **Project Work — Data Quality:** Identify restaurants with missing information, inaccurate GPS coordinates, or inconsistent data.
- **Project Work — Recommendation Relevance:** Combine multiple criteria rather than relying only on restaurant ratings.
- **Project Work — Itinerary Feasibility:** Consider the order of destinations, geographical distance, and travel time.
- **Project Work — Deployment Scope:** Prioritize local development and testing before considering AWS deployment.
