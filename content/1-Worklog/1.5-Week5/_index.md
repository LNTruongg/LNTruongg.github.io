---
title: "Week 5 Worklog"
date: 2026-10-12
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

- Understand Load Balancing and why traffic needs to be distributed across multiple servers.
- Learn about Elastic Load Balancing, particularly Application Load Balancer (ALB).
- Understand the roles of Listeners, Target Groups, and Health Checks in ALB.
- Explore Auto Scaling Groups (ASG), Launch Templates, and how EC2 instance capacity can be adjusted based on demand.
- Analyze a basic architecture combining ALB and ASG while reviewing potential AWS costs before performing practical exercises.
- Continue exploring the LoveSpot project, focusing on user interface layouts and the application's main features.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about Load Balancing and Single Points of Failure. Explore Elastic Load Balancing (ELB), its purpose, and the basic differences between Application Load Balancers and Network Load Balancers. | 2026-10-12 | 2026-10-12 | [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html) |
| 3 | Learn how Application Load Balancers operate at Layer 7. Explore Listeners, Listener Rules, and Target Groups, including examples of routing requests based on URL paths. | 2026-10-13 | 2026-10-13 | [Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/), [ALB Listeners](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html) |
| 4 | Study Health Checks and how ALB determines whether targets are Healthy or Unhealthy. Analyze request flows from Clients through ALB to EC2 instances in Target Groups across multiple Availability Zones. | 2026-10-14 | 2026-10-14 | [ALB Target Groups](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html), [Target Group Health Checks](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html) |
| 5 | Understand the differences between Scale Up/Down and Scale Out/In. Learn about Amazon EC2 Auto Scaling, Auto Scaling Groups, and Launch Templates, including AMIs, Instance Types, and Security Groups. | 2026-10-15 | 2026-10-15 | [EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html), [Launch Templates](https://docs.aws.amazon.com/autoscaling/ec2/userguide/launch-templates.html) |
| 6 | Explore Minimum, Maximum, and Desired Capacity settings in ASG. Review examples of Target Tracking Scaling based on CPU utilization and how ASG can launch additional EC2 instances when necessary. | 2026-10-16 | 2026-10-16 | [ASG Scaling Limits](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-capacity-limits.html), [Target Tracking Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html) |
| 7 | Review the week's topics and sketch an architecture combining ALB and ASG using draw.io. Learn how EC2 instances are registered with Target Groups and review AWS pricing. Avoid deploying ALB or EC2 instances through ASG to prevent unnecessary costs. **Project Work:** Continue exploring LoveSpot by sketching interface layouts and identifying the main features for searching, recommending places, and creating itineraries. | 2026-10-17 | 2026-10-17 | [ALB with Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-load-balancer.html), [ELB Pricing](https://aws.amazon.com/elasticloadbalancing/pricing/), [EC2 Auto Scaling Pricing](https://aws.amazon.com/ec2/autoscaling/pricing/) |

### Week 5 Results:

**Knowledge Gained:**

- Understood how Load Balancers distribute requests across multiple servers, reducing dependence on a single EC2 instance and improving application availability.
- Learned that Elastic Load Balancing offers different types of load balancers. Application Load Balancer is designed for HTTP/HTTPS applications, while Network Load Balancer primarily operates at Layer 4.
- Understood the basic request flow `Client → ALB → Listener Rule → Target Group → EC2` and how ALB can route requests based on URL paths.
- Learned how Health Checks monitor target status and help ALB direct requests to healthy targets during normal operation.
- Distinguished Scale Up/Down, which changes server capacity, from Scale Out/In, which increases or decreases the number of servers.
- Understood how ASG uses Launch Templates to define EC2 configurations and maintain the Desired Capacity within Minimum and Maximum limits.
- Became familiar with Target Tracking Scaling and the role of CloudWatch Metrics in supporting automatic scaling.

**Learning Activities and Practice:**

- Analyzed an example website with two EC2 instances behind an ALB to understand request distribution and what happens when a target fails a Health Check.
- Sketched a simple architecture using draw.io, including Clients, an ALB, Target Groups, and EC2 instances managed by an Auto Scaling Group. Connected these concepts with VPC and Availability Zone knowledge from previous weeks.
- Practiced with a hypothetical configuration of `Min = 1`, `Desired = 2`, and `Max = 3` to understand how ASG manages the number of EC2 instances.
- Reviewed documentation on integrating ALB with ASG instead of running a practical lab that required multiple EC2 instances.
- Studied the costs associated with ALB, EC2, and related AWS resources. This week's activities focused on documentation and architecture analysis without deploying the actual infrastructure to avoid unexpected charges.

**LoveSpot Project Activities:**

- Continued exploring the user interface design for LoveSpot, an application that recommends restaurants and helps users plan itineraries in Ho Chi Minh City.
- Sketched layouts for the main screens, focusing on user input, searching for places, and displaying recommendations based on user preferences.
- Considered how users would move from selecting places to generating an itinerary, with the goal of creating a clear and convenient user experience.
- Began identifying the data needed for the recommendation system, such as venue information, locations, and user preferences. This was still an early planning stage, and no AWS infrastructure had been deployed for LoveSpot.

**Challenges Encountered and Solutions:**

- Initially found it difficult to distinguish Listeners from Target Groups because both are involved in ALB request processing. After reviewing the request flow, I understood that Listeners receive connections and evaluate rules, while Target Groups contain the targets selected to handle requests.
- Had some difficulty distinguishing the roles of Load Balancers and Auto Scaling Groups because both relate to scalability. Comparing their responsibilities in an architecture diagram helped me understand that ALB distributes traffic, while ASG manages the number of EC2 instances based on demand.