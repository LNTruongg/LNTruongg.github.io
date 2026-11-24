
---
title: "Worklog Week 11"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

- Learn about AWS Elastic Beanstalk and how it supports web application deployment.
- Become familiar with Docker, Docker Images, Containers, and the roles of Amazon ECR and Amazon ECS.
- Understand the basic components of Amazon ECS and consider potential costs before deploying applications on AWS.
- **Project Work:** Continue developing the restaurant recommendation and itinerary planning application for Ho Chi Minh City.
- **Project Work:** Review the integration between restaurant data, the recommendation system, Backend, and Frontend.
- **Project Work:** Evaluate recommendation results, itinerary generation, and the handling of incomplete or unsuitable data.

### Tasks to Complete This Week:

| Day | Task | Start Date | Completion Date | References |
| --- | --- | --- | --- | --- |
| Monday | Learn about AWS Elastic Beanstalk, including Application, Environment, and Platform. Explore how web applications are deployed and which underlying AWS resources may incur costs. | 23/11/2026 | 23/11/2026 | [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html), [Elastic Beanstalk Concepts](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html) |
| Tuesday | Learn about Docker Images and Containers. Explore Amazon ECR for storing container images and Amazon ECS for running and managing containers. Study Cluster, Task Definition, Service, and Fargate without creating actual AWS resources. | 24/11/2026 | 24/11/2026 | [Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html), [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) |
| Wednesday | **Project Work:** Review the architecture of the restaurant recommendation and itinerary planning application for Ho Chi Minh City. Examine the roles of the Frontend, Backend, recommendation system, and restaurant dataset. Identify the components that need to be integrated to generate complete itineraries. | 25/11/2026 | 25/11/2026 | Project source code and architecture documentation |
| Thursday | **Project Work:** Examine the data flow from user requests to the recommendation system. Review inputs such as budget, preferences, location, and GPS coordinates. Check how restaurant data is retrieved and provided for the recommendation process. | 26/11/2026 | 26/11/2026 | Project dataset, Backend APIs, and data processing documentation |
| Friday | **Project Work:** Continue developing and reviewing API integration between system components. Examine input and output data formats, restaurant recommendation results, and how generated itineraries are presented in the user interface. | 27/11/2026 | 27/11/2026 | Frontend, Backend, and recommendation system source code |
| Saturday | **Project Work:** Test restaurant recommendations and itinerary generation using different scenarios. Evaluate restaurant relevance, geographical distances, and the order of destinations. Record issues and limitations for improvement in the following week. | 28/11/2026 | 28/11/2026 | Project source code, dataset, and test scenarios |

### Expected Outcomes for Week 11:

**AWS Knowledge Acquired:**

- Understand how AWS Elastic Beanstalk simplifies web application deployment and management, while recognizing that underlying infrastructure resources may still incur costs.
- Distinguish between a Docker Image, which packages an application and its dependencies, and a Container, which is a running instance created from an Image.
- Understand that Amazon ECR stores container images, while Amazon ECS runs and manages containers on AWS.
- Become familiar with Cluster, Task Definition, Task, Service, and the two container deployment options: Amazon EC2 and AWS Fargate.
- Gain foundational knowledge for evaluating possible AWS deployment approaches for the application in the future.

**Expected Project Outcomes:**

- **Project Work:** Develop a clearer understanding of how the Frontend, Backend, recommendation system, and restaurant dataset work together.
- **Project Work:** Identify the processing flow from user inputs to restaurant recommendations and itinerary generation.
- **Project Work:** Review restaurant data and the use of GPS coordinates in recommendations and map visualization.
- **Project Work:** Examine data exchange through APIs between system components and identify areas that require improvement.
- **Project Work:** Prepare test scenarios to evaluate recommendation quality and itinerary feasibility before finalizing the application.

**Challenges and Proposed Solutions:**

- **AWS Knowledge:** Elastic Beanstalk, ECR, and ECS serve different purposes. Distinguish between application deployment, container image storage, and container orchestration, while considering potential costs before using these services.
- **Project Work — System Integration:** The Frontend, Backend, and recommendation system must use consistent input and output data structures to avoid integration errors.
- **Project Work — Restaurant Data:** Restaurants with missing or inaccurate GPS coordinates may affect map visualization and itinerary generation. Validate location data before using it.
- **Project Work — Recommendation Quality:** Recommendations should satisfy user requirements while considering budget, geographical distance, and the suitability of selected restaurants.
- **Project Work — Testing:** Test multiple input scenarios, record issues, and make gradual improvements instead of evaluating the system using only one sample itinerary.
- **Project Work — Deployment Scope:** Prioritize local development and integration testing. Consider AWS deployment separately based on actual requirements and estimated costs.
