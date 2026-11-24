---
title: "Week 9 Worklog"
date: 2026-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

- Learn about AWS messaging and event-driven services.
- Understand the differences between Amazon SQS, SNS, and SES.
- Learn how Amazon EventBridge processes events.
- Review service costs and common use cases.
- Continue working on LoveSpot, focusing on data and communication between system components.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about Amazon SQS and how messages are stored in a Queue for later processing. Review an order-processing example. | 2026-11-09 | 2026-11-09 | [Amazon SQS](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html) |
| 3 | Study Standard Queues, FIFO Queues, and Visibility Timeout. Review how messages are received, processed, and deleted. | 2026-11-10 | 2026-11-10 | [SQS Visibility Timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html) |
| 4 | Learn about Amazon SNS, Topics, and Subscriptions. Review how notifications can be delivered to multiple recipients. | 2026-11-11 | 2026-11-11 | [Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/) |
| 5 | Learn about Amazon SES, sending application emails, and SES Sandbox limitations. No actual emails were sent. | 2026-11-12 | 2026-11-12 | [Amazon SES](https://docs.aws.amazon.com/ses/latest/dg/Welcome.html), [SES Sandbox](https://docs.aws.amazon.com/ses/latest/dg/request-production-access.html) |
| 6 | Explore Amazon EventBridge, Event Buses, Rules, and Targets. **Project Work:** Review restaurant data and how it could be used by LoveSpot's recommendation system. | 2026-11-13 | 2026-11-13 | [Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html) |
| 7 | Review SQS, SNS, SES, and EventBridge, and check AWS pricing. **Project Work:** Study how to connect the Frontend, Backend, and recommendation system in preparation for feature integration. | 2026-11-14 | 2026-11-14 | [AWS Messaging Decision Guide](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/sns-or-sqs-or-eventbridge.html), [EventBridge Pricing](https://aws.amazon.com/eventbridge/pricing/) |

### Week 9 Results:

**Knowledge Gained:**

- Understood how SQS stores messages in a Queue until they are ready to be processed.
- Learned the differences between Standard and FIFO Queues and the purpose of Visibility Timeout.
- Understood how SNS uses Topics and Subscriptions to send notifications.
- Learned that SES is used for sending emails and has restrictions when an account is in the Sandbox.
- Understood how EventBridge uses Rules to route events to suitable Targets.

**Learning Activities and Practice:**

- Reviewed examples of message processing with SQS and sending notifications through SNS.
- Compared SNS and EventBridge using simple scenarios.
- Reviewed AWS pricing. No Queues, Topics, Event Rules, or actual email-sending resources were created to avoid unnecessary costs.

**LoveSpot Project Activities:**

- Reviewed how restaurant information, reviews, and other data could be organized for the recommendation system.
- Explored how the Frontend sends user information to the Backend and receives recommendation results.
- Prepared for connecting LoveSpot's components and testing its features in the following weeks.

**Challenges Encountered and Solutions:**

- Initially found Visibility Timeout confusing because a received message still remains in the Queue. Reviewing examples helped me understand why a message should be deleted after successful processing.
- Had difficulty distinguishing SNS from EventBridge. After reviewing examples, I understood that SNS is commonly used to distribute notifications, while EventBridge can filter and route events based on Rules.