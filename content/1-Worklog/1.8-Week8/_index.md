---
title: "Week 8 Worklog"
date: 2026-11-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

- Learn about DNS and how Amazon Route 53 manages domain names.
- Understand common DNS Records, Hosted Zones, and TTL.
- Learn how CloudFront uses CDN and caching to deliver website content.
- Explore how Route 53, CloudFront, and S3 work together.
- Continue working on the LoveSpot interface and its basic features.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about DNS, Route 53, and common records such as A, CNAME, and MX. | 2026-11-02 | 2026-11-02 | [Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html) |
| 3 | Study Public Hosted Zones, Private Hosted Zones, and TTL. | 2026-11-03 | 2026-11-03 | [Route 53 Hosted Zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-working-with.html) |
| 4 | Explore Simple, Weighted, and Failover Routing, along with Health Checks. Read documentation without creating resources. | 2026-11-04 | 2026-11-04 | [Route 53 Routing Policies](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html) |
| 5 | Learn about CDN, CloudFront, Origins, Edge Locations, and content caching. | 2026-11-05 | 2026-11-05 | [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 6 | Learn about Cache Hits, Cache Misses, and how CloudFront retrieves files from S3. **Project Work:** Continue adjusting the LoveSpot interface layout using React/Vite. | 2026-11-06 | 2026-11-06 | [How CloudFront Works](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowCloudFrontWorks.html) |
| 7 | Review Route 53, CloudFront, and S3. Check AWS pricing without creating resources. **Project Work:** Review how venue lists and recommendation inputs are displayed. | 2026-11-07 | 2026-11-07 | [Route 53 Pricing](https://aws.amazon.com/route53/pricing/), [CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/) |

### Week 8 Results:

**Knowledge Gained:**

- Understood how DNS resolves domain names and how Route 53 manages DNS records.
- Learned the differences between A Records, CNAME, and MX, along with Hosted Zones and TTL.
- Understood that CloudFront is a CDN that delivers content through Edge Locations.
- Learned the differences between Cache Hits and Cache Misses.
- Understood that Route 53 handles DNS, CloudFront delivers content, and S3 can store the original files.

**Learning Activities and Practice:**

- Reviewed examples of DNS Records and routing policies.
- Studied how S3 and CloudFront can work together to serve a static website.
- Reviewed AWS pricing without creating Hosted Zones, Health Checks, or CloudFront Distributions to avoid unnecessary charges.

**LoveSpot Project Activities:**

- Continued reviewing and adjusting the LoveSpot interface, focusing on user input and venue search.
- Explored how restaurant lists and recommendation data should be displayed to make them easier for users to browse and select.
- Reviewed the user flow in preparation for connecting the interface with the Backend and recommendation system in the following weeks.

**Challenges Encountered and Solutions:**

- Initially found it difficult to remember different DNS Record types. Reviewing simple examples helped me distinguish A Records, CNAME, and MX.
- When learning about CloudFront, I wondered why users could still see old content after a website update. Studying caching and TTL helped me understand the reason.