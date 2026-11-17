---
title: "Week 11 Worklog"
date: 2026-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

- Learn about AWS Elastic Beanstalk and how it helps deploy web applications.
- Become familiar with Docker, Containers, and Docker Images.
- Understand that Amazon ECR stores images, while Amazon ECS runs and manages containers.
- Learn the basic components of ECS and check costs before hands-on practice.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Elastic Beanstalk and how it helps deploy web applications to AWS without manually setting up every infrastructure component. | 23/11/2026 | 23/11/2026 | [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html) |
| 3 | Learn about Applications, Environments, and Platforms in Elastic Beanstalk. Review an example of updating an application and why running environments can still incur charges. | 24/11/2026 | 24/11/2026 | [Elastic Beanstalk Concepts](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html), [Elastic Beanstalk Pricing](https://aws.amazon.com/elasticbeanstalk/pricing/) |
| 4 | Learn about Docker and Containers. Understand the difference between Docker Images and Containers, and read a simple Dockerfile example used to package an application. | 25/11/2026 | 25/11/2026 | [Containers on Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-configuration.html) |
| 5 | Learn about Amazon ECR, Repositories, and Image Tags. Review how images are stored in ECR for other services to use, without creating a real Repository. | 26/11/2026 | 26/11/2026 | [Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html) |
| 6 | Learn about Amazon ECS and the concepts of Clusters, Task Definitions, Tasks, and Services. Read about running containers on EC2 and Fargate without launching a Task. | 27/11/2026 | 27/11/2026 | [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html), [ECS Task Definitions](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definitions.html) |
| 7 | Review the differences between Elastic Beanstalk, ECR, and ECS. Go over the process from a Docker Image to ECR and then ECS, and read pricing information to avoid unexpected charges. | 28/11/2026 | 28/11/2026 | [Amazon ECS Pricing](https://aws.amazon.com/ecs/pricing/), [Amazon ECR Pricing](https://aws.amazon.com/ecr/pricing/) |

### Expected Week 11 Achievements:

**Knowledge to Gain:**

- Understand that Elastic Beanstalk makes application deployment and management easier, but resources such as EC2 instances or Load Balancers can still incur charges.
- Learn that a Docker Image packages an application and what it needs to run, while a Container is a running instance created from an Image.
- Understand that ECR stores Container Images, while ECS helps run and manage Containers on AWS.
- Become familiar with ECS Clusters, Task Definitions, Tasks, and Services, and learn that ECS can use EC2 or Fargate to run applications.

**Review and Learning with the Materials:**

- Review an example of deploying a web application using Elastic Beanstalk and the AWS resources created behind it.
- Read a Dockerfile example and learn how an Image can be stored in ECR and then used by ECS.
- Focus on documentation without creating Elastic Beanstalk Environments, ECR Repositories, or running ECS Tasks to avoid unexpected costs.

**Topics to Watch Out For and How to Study Them:**

- Images and Containers are closely related. A simple way to remember the difference is that an Image packages an application, while a Container is a running instance of that Image.
- ECR and ECS also have similar names but different roles. Reviewing the process helps: ECR stores Images, and ECS uses those Images to run and manage Containers.