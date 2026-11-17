
---
title: "Week 10 Worklog"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

- Learn how Amazon CloudWatch monitors AWS services.
- Become familiar with Metrics, Logs, and Alarms.
- Understand what AWS CloudTrail records in an AWS account.
- Learn the basic roles of security services such as IAM Identity Center, KMS, Secrets Manager, GuardDuty, and WAF.
- Review the topics and check costs before using AWS services.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Amazon CloudWatch and Metrics. Review an example of monitoring EC2 CPU usage without creating a new instance. | 16/11/2026 | 16/11/2026 | [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) |
| 3 | Learn about CloudWatch Logs and Alarms. Read an example of an alert when CPU usage passes a threshold; do not create an Alarm to avoid unexpected charges. | 17/11/2026 | 17/11/2026 | [CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html), [CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Alarms.html) |
| 4 | Learn about AWS CloudTrail and Event history. Review how to look up actions such as logins or resource changes, and compare CloudTrail with CloudWatch. | 18/11/2026 | 18/11/2026 | [CloudTrail Event History](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html) |
| 5 | Explore IAM Identity Center, AWS KMS, and Secrets Manager at a basic level: managing access, encryption keys, and application secrets. | 19/11/2026 | 19/11/2026 | [IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html), [AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html), [Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/) |
| 6 | Learn about Amazon GuardDuty and AWS WAF. Read examples of detecting suspicious activity and filtering unwanted website requests without enabling these services. | 20/11/2026 | 20/11/2026 | [Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html), [AWS WAF](https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html) |
| 7 | Review CloudWatch, CloudTrail, and the security services covered this week. Check pricing and note which features may have extra charges before hands-on practice. | 21/11/2026 | 21/11/2026 | [CloudWatch Pricing](https://aws.amazon.com/cloudwatch/pricing/), [CloudTrail Pricing](https://aws.amazon.com/cloudtrail/pricing/), [GuardDuty Pricing](https://aws.amazon.com/guardduty/pricing/) |

### Expected Week 10 Achievements:

**Knowledge to Gain:**

- Understand that CloudWatch monitors system health through Metrics, Logs, and Alarms.
- Learn that Metrics are values such as CPU usage, Logs record activity, and Alarms notify users when a threshold is reached.
- Understand that CloudTrail helps review management actions in an AWS account. Event history provides free access to the last 90 days of management events.
- Learn that IAM Identity Center manages access, KMS manages encryption keys, and Secrets Manager stores application secrets.
- Understand that GuardDuty helps detect suspicious activity, while AWS WAF filters HTTP/HTTPS requests to web applications.

**Review and Learning with the Materials:**

- Review an example of a high-CPU alert and an example of looking up an event in CloudTrail.
- Compare CloudWatch and CloudTrail through simple situations.
- Focus on documentation without creating Alarms, Trails, KMS keys, Secrets, or enabling GuardDuty/WAF to avoid unnecessary costs.

**Topics to Watch Out For and How to Study Them:**

- Metrics, Logs, and CloudTrail all relate to monitoring, but have different purposes. A simple way to remember them is: Metrics show CPU usage, Logs record application errors, and CloudTrail helps show who performed an AWS action.
- There are many security services with different names. Learning their basic purposes, such as protecting passwords, managing encryption keys, or detecting threats, is easier than memorizing every feature.
