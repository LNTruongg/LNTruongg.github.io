---
title: "Week 11 Worklog"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

- Learn about AWS Elastic Beanstalk and web application deployment.
- Understand Docker, Amazon ECR, and Amazon ECS.
- Learn the basic components of ECS and their costs.
- Work on LoveSpot: review the AWS deployment, architecture diagram, and demo video.
- Test venue recommendations, itinerary generation, and connections between system components.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about Elastic Beanstalk, Applications, Environments, Platforms, and related AWS costs. | 2026-11-23 | 2026-11-23 | [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html), [Elastic Beanstalk Concepts](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html) |
| 3 | Learn about Docker Images, Containers, Amazon ECR, and ECS. Study Clusters, Task Definitions, Services, and Fargate without creating test resources. | 2026-11-24 | 2026-11-24 | [Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html), [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) |
| 4 | **Project Work:** Review the deployed LoveSpot application on AWS. Compare the draw.io architecture diagram with the AWS services actually used. | 2026-11-25 | 2026-11-25 | LoveSpot source code, AWS resources, and architecture diagram |
| 5 | **Project Work:** Review the recorded demo video and document the main steps of using the application for the Workshop report. | 2026-11-26 | 2026-11-26 | Demo video and project documentation |
| 6 | **Project Work:** Test connections between the Frontend, Backend, and recommendation system in the deployed application. Check venue recommendations and generated itineraries. | 2026-11-27 | 2026-11-27 | LoveSpot source code and test cases |
| 7 | **Project Work:** Organize deployment documentation, review monitoring information, and estimate AWS costs. Note any remaining issues. | 2026-11-28 | 2026-11-28 | Workshop documentation, [AWS Pricing](https://aws.amazon.com/pricing/), [CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) |

### Week 11 Results:

**AWS Knowledge:**

- Understood that Elastic Beanstalk simplifies application deployment, but the underlying AWS resources may still incur charges.
- Learned the difference between Docker Images and Containers.
- Understood that ECR stores container images, while ECS runs and manages containers.
- Learned about Clusters, Task Definitions, Services, and Fargate.

**LoveSpot Project Activities:**

- Deployed LoveSpot to AWS and completed the system architecture diagram.
- Recorded a demo video showing how to use the application.
- Continued reviewing the data flow between the Frontend, Backend, and recommendation system.
- Prepared to finalize the Workshop documentation, test the deployed application, and review AWS costs.

**Challenges and Solutions:**

- API connections and environment settings need to be checked to keep the deployed application running properly.
- The architecture diagram must match the AWS resources actually used.
- AWS costs should be monitored, and unused resources should be reviewed.