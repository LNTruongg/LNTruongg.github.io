
---
title: "Week 5 Worklog"
date: 2026-10-12
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

- Learn about Load Balancing and why traffic needs to be distributed across multiple servers.
- Become familiar with Elastic Load Balancing, especially Application Load Balancers (ALBs).
- Understand the roles of Listeners, Target Groups, and Health Checks in an ALB.
- Explore Auto Scaling Groups (ASGs), Launch Templates, and how EC2 capacity changes with demand.
- Analyze a simple architecture combining ALB and ASG, and review potential costs before hands-on practice.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Load Balancing and the Single Point of Failure concept. Explore Elastic Load Balancing (ELB), its purpose, and the basic differences between Application Load Balancers and Network Load Balancers. | 12/10/2026 | 12/10/2026 | [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html) |
| 3 | Learn how Application Load Balancers work at Layer 7. Explore Listeners, Listener Rules, and Target Groups, including an example of routing requests based on URL paths. | 13/10/2026 | 13/10/2026 | [Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/), [ALB Listeners](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html) |
| 4 | Learn about Health Checks and how an ALB identifies Healthy and Unhealthy Targets. Analyze the request flow from a Client through an ALB to EC2 instances in a Target Group across Availability Zones. | 14/10/2026 | 14/10/2026 | [ALB Target Groups](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html), [Target Group Health Checks](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html) |
| 5 | Learn the differences between Scale Up/Down and Scale Out/In. Explore Amazon EC2 Auto Scaling, Auto Scaling Groups, and Launch Templates, including AMIs, Instance Types, and Security Groups. | 15/10/2026 | 15/10/2026 | [EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html), [Launch Templates](https://docs.aws.amazon.com/autoscaling/ec2/userguide/launch-templates.html) |
| 6 | Learn about the Minimum, Maximum, and Desired Capacity settings of an ASG. Review an example of Target Tracking Scaling based on CPU utilization and how an ASG can add EC2 instances when needed. | 16/10/2026 | 16/10/2026 | [ASG Scaling Limits](https://docs.aws.amazon.com/autoscaling/ec2/userguide/asg-capacity-limits.html), [Target Tracking Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html) |
| 7 | Review the week's topics and sketch an architecture combining ALB and ASG using draw.io. Learn how EC2 instances join Target Groups and check AWS pricing. Do not create an ALB or an ASG running EC2 instances to avoid additional charges. | 17/10/2026 | 17/10/2026 | [ALB with Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-load-balancer.html), [ELB Pricing](https://aws.amazon.com/elasticloadbalancing/pricing/), [EC2 Auto Scaling Pricing](https://aws.amazon.com/ec2/autoscaling/pricing/) |

### Week 5 Achievements:

**Knowledge Gained:**

- Understood that a Load Balancer distributes requests across multiple servers, reduces dependence on a single EC2 instance, and helps improve application availability.
- Learned that Elastic Load Balancing provides several types of load balancers. Application Load Balancers are suitable for HTTP/HTTPS applications, while Network Load Balancers mainly operate at Layer 4.
- Understood the basic flow `Client → ALB → Listener Rule → Target Group → EC2` and how an ALB can route requests based on URL paths.
- Learned that Health Checks allow an ALB to monitor Targets and normally send requests to healthy ones.
- Distinguished Scale Up/Down, which changes server resources, from Scale Out/In, which changes the number of servers.
- Understood that an ASG uses a Launch Template to define EC2 settings and maintains its Desired Capacity within Minimum and Maximum limits.
- Became familiar with Target Tracking Scaling and the role of CloudWatch Metrics in automatic scaling.

**Learning and Practice with the Materials:**

- Analyzed an example website with two EC2 instances behind an ALB to understand request distribution and what happens when a Target fails a Health Check.
- Sketched a simple architecture in draw.io with a Client, ALB, Target Group, and EC2 instances in an Auto Scaling Group, connecting it to the VPC and Availability Zone concepts from previous weeks.
- Worked through a hypothetical example with `Min = 1`, `Desired = 2`, and `Max = 3` to understand how an ASG adjusts EC2 capacity.
- Read the guide for connecting an ALB to an ASG instead of running a lab that launches multiple EC2 instances.
- Learned that ALBs are billed based on running time and LCU usage. EC2 Auto Scaling has no additional service fee, but EC2, CloudWatch, and related resources can still incur charges. Therefore, this week's activities focused on learning and diagram analysis rather than deploying the architecture.

**Challenges Encountered and Solutions:**

- At first, Listeners and Target Groups were easy to confuse because both take part in routing ALB requests. Drawing the request flow helped clarify that a Listener accepts connections and evaluates Rules, while a Target Group contains the Targets that handle requests.
- It was initially unclear how a Load Balancer differs from an Auto Scaling Group because both support scalability. Comparing their responsibilities in a diagram helped show that an ALB distributes traffic, while an ASG manages the number of EC2 instances according to demand.
