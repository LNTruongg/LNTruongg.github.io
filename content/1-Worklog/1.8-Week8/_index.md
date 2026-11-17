
---
title: "Week 8 Worklog"
date: 2026-11-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

- Learn about DNS and how Amazon Route 53 manages domain names.
- Become familiar with DNS Records, Hosted Zones, and TTL.
- Understand what a CDN is and how Amazon CloudFront helps websites load content faster.
- Review how Route 53, CloudFront, and S3 work together, while keeping AWS costs in mind.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about DNS and Route 53. Read about common records such as A, CNAME, and MX. | 02/11/2026 | 02/11/2026 | [Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html) |
| 3 | Learn about Hosted Zones, the difference between Public and Private Hosted Zones, and the meaning of TTL. | 03/11/2026 | 03/11/2026 | [Route 53 Hosted Zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-working-with.html) |
| 4 | Learn the basics of Simple, Weighted, and Failover Routing, along with Health Checks. Read the documentation without creating resources. | 04/11/2026 | 04/11/2026 | [Route 53 Routing Policies](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html) |
| 5 | Learn about CDNs and CloudFront. Explore Origins, Edge Locations, and how CloudFront caches website content. | 05/11/2026 | 05/11/2026 | [Amazon CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 6 | Learn about Cache Hits and Cache Misses. Review an example of CloudFront getting images or static files from S3 and delivering them to users. | 06/11/2026 | 06/11/2026 | [How CloudFront Works](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowCloudFrontWorks.html) |
| 7 | Review Route 53 and CloudFront, including how they work with S3. Check AWS pricing without registering a domain or creating a CloudFront Distribution. | 07/11/2026 | 07/11/2026 | [Route 53 Pricing](https://aws.amazon.com/route53/pricing/), [CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/) |

### Week 8 Achievements:

**Knowledge Gained:**

- Understood that DNS helps turn domain names into information used to reach servers, while Route 53 manages domains and DNS records.
- Learned that A Records point to IPv4 addresses, CNAME Records point to other domain names, and MX Records are used for email.
- Understood that Hosted Zones contain DNS Records and that TTL affects how long records stay cached.
- Learned that CloudFront is a CDN that delivers content through Edge Locations to help users access websites faster.
- Understood the basic roles of each service: Route 53 handles DNS, CloudFront delivers content, and S3 can store the original files.

**Review and Learning with the Materials:**

- Reviewed simple DNS Record examples and how Route 53 routes website traffic.
- Revisited the S3 static website topic from Week 3 and learned how CloudFront can help deliver images and static files.
- Checked AWS pricing. Did not buy a domain or create Hosted Zones, Health Checks, or CloudFront Distributions to avoid extra charges.

**Challenges Encountered and Solutions:**

- There are several DNS Record types, so remembering what each one does took some time. Reading simple examples helped me remember common records such as A, CNAME, and MX.
- While learning about CloudFront, I wondered why users might still see old content after a website update. Reading about caching and TTL helped me understand that content can remain cached for a period of time.
