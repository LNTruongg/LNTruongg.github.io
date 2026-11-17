
---
title: "Week 9 Worklog"
date: 2026-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

- Learn how AWS services send and receive messages.
- Become familiar with Amazon SQS, SNS, and SES and their basic use cases.
- Understand how Amazon EventBridge helps services respond to events.
- Learn when to use each service and check costs before hands-on practice.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Amazon SQS and how messages are stored in a Queue for later processing. Review an example of an online store's order queue. | 09/11/2026 | 09/11/2026 | [Amazon SQS](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html) |
| 3 | Learn about Standard Queues, FIFO Queues, and Visibility Timeout. Read an example explaining why a message should be deleted after processing. | 10/11/2026 | 10/11/2026 | [SQS Visibility Timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html) |
| 4 | Learn about Amazon SNS, Topics, and Subscriptions. Review an example of sending one notification to several people or services. | 11/11/2026 | 11/11/2026 | [Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/) |
| 5 | Learn about Amazon SES and how applications send confirmation or notification emails. Read about email verification and Sandbox limits without sending actual emails. | 12/11/2026 | 12/11/2026 | [Amazon SES](https://docs.aws.amazon.com/ses/latest/dg/Welcome.html), [SES Sandbox](https://docs.aws.amazon.com/ses/latest/dg/request-production-access.html) |
| 6 | Learn about Amazon EventBridge, Event Buses, Rules, and Targets. Review an example of an AWS event being sent to Lambda or SQS when it matches a rule. | 13/11/2026 | 13/11/2026 | [Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html) |
| 7 | Review and compare SQS, SNS, SES, and EventBridge using simple examples. Read about pricing and Free Tier limits without creating Queues, Topics, or Event Rules on AWS. | 14/11/2026 | 14/11/2026 | [AWS Messaging Decision Guide](https://docs.aws.amazon.com/decision-guides/latest/decision-guides/sns-or-sqs-or-eventbridge.html), [EventBridge Pricing](https://aws.amazon.com/eventbridge/pricing/) |

### Week 9 Achievements:

**Knowledge Gained:**

- Understood that SQS stores messages in a Queue so a consumer can process them when ready, without both parts of the system needing to run at the same time.
- Learned that Standard Queues suit many common tasks, while FIFO Queues help keep messages in order within a message group. Understood the basic purpose of Visibility Timeout.
- Learned that SNS uses Topics and Subscriptions to send one notification to several destinations, such as email or SQS.
- Understood that SES can send emails from an application, such as sign-up confirmation emails. Sandbox accounts have recipient restrictions and require appropriate address verification.
- Learned that EventBridge receives events and uses Rules to send them to suitable Targets, such as Lambda or SQS.

**Review and Learning with the Materials:**

- Reviewed an online ordering example where SQS holds orders until a consumer is ready to process them.
- Compared how SNS sends notifications with how EventBridge routes events based on rules.
- Checked pricing and free usage limits. This week focused on reading documentation, without creating AWS resources or sending emails to avoid unexpected costs.

**Challenges Encountered and Solutions:**

- Visibility Timeout took extra reading because a message stays in the Queue even after it has been received. An example showing that messages are deleted after processing helped me understand why.
- SNS and EventBridge can both send information to other services, so choosing between them was not immediately clear. The examples showed me that SNS is useful for Topic-based notifications, while EventBridge helps filter and route events using Rules.
