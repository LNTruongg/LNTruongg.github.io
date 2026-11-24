---
title: "Week 10 Worklog"
date: 2026-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

- Learn about CloudWatch, CloudTrail, and basic AWS security services.
- Understand how to monitor system activities and control costs.
- Work on LoveSpot: review venue data and improve the recommendation process.
- Test itinerary recommendations with different user requirements.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about CloudWatch Metrics, Logs, Alarms, and CloudTrail Event History. Understand the differences between system monitoring and recording AWS activities. | 2026-11-16 | 2026-11-16 | [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html), [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html) |
| 3 | Learn about IAM Identity Center, KMS, Secrets Manager, GuardDuty, and WAF. Review pricing without enabling paid services. | 2026-11-17 | 2026-11-17 | [AWS Security](https://aws.amazon.com/security/), [AWS Pricing](https://aws.amazon.com/pricing/) |
| 4 | **Project Work:** Review LoveSpot requirements, including location, budget, food preferences, and available time. | 2026-11-18 | 2026-11-18 | LoveSpot requirements and source code |
| 5 | **Project Work:** Review restaurant data in Ho Chi Minh City, focusing on addresses, GPS coordinates, and reviews. Check venues with missing information. | 2026-11-19 | 2026-11-19 | LoveSpot dataset and data-processing notes |
| 6 | **Project Work:** Review how restaurants are ranked based on preferences, budget, and distance. Study how to arrange selected places into a suitable itinerary. | 2026-11-20 | 2026-11-20 | Source code and recommendation system notes |
| 7 | **Project Work:** Test recommendations with different budgets, locations, and preferences. Note cases that need improvement. | 2026-11-21 | 2026-11-21 | LoveSpot source code and test cases |

### Week 10 Results:

**AWS Knowledge:**

- Understood how CloudWatch monitors Metrics, Logs, and Alarms.
- Learned how CloudTrail records activities related to AWS accounts and resources.
- Understood the basic purposes of IAM Identity Center, KMS, Secrets Manager, GuardDuty, and WAF.
- Reviewed service costs without enabling additional AWS services.

**LoveSpot Project Activities:**

- Reviewed the input requirements for venue recommendations and itinerary generation.
- Checked restaurant data quality, especially addresses, GPS coordinates, and reviews.
- Reviewed the recommendation logic using multiple criteria instead of relying only on ratings.
- Tested different budgets, locations, and preferences to identify areas for improvement.

**Challenges and Solutions:**

- Some venues had missing information or GPS coordinates that needed checking. Invalid data should be filtered before generating recommendations.
- Choosing suitable restaurants was not enough to create a good itinerary. Distance and visit order also needed attention.
- Focused on local testing before deploying the system to AWS.