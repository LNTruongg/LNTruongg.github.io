
---
title: "Week 4 Worklog"
date: 2026-10-05
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

- Learn about Amazon VPC and basic networking components in AWS.
- Become familiar with CIDR, Subnets, and the differences between Public and Private Subnets.
- Understand the roles of Route Tables, Internet Gateways, and NAT Gateways.
- Compare Security Groups and Network ACLs for controlling network traffic.
- Explore VPC Endpoints and VPC Peering, and practice designing a simple VPC diagram.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Amazon VPC and how VPCs relate to Regions and Availability Zones. Become familiar with CIDR and how IP ranges are divided into Subnets. | 05/10/2026 | 05/10/2026 | [Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html), [VPC IP Addressing](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-ip-addressing.html) |
| 3 | Learn about Public Subnets, Private Subnets, Route Tables, and Internet Gateways. Review an example of the `0.0.0.0/0` route pointing to an Internet Gateway. | 06/10/2026 | 06/10/2026 | [Subnet Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/subnet-route-tables.html), [Internet Gateway](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| 4 | Learn how a NAT Gateway allows resources in Private Subnets to access the Internet. Read about NAT Gateway charges and study the diagram without creating this resource. | 07/10/2026 | 07/10/2026 | [NAT Devices](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat.html), [NAT Gateway Pricing](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-pricing.html) |
| 5 | Review Security Groups from Week 1 and learn about Network ACLs. Compare their scope, Allow/Deny Rules, and Stateful/Stateless behavior. | 08/10/2026 | 08/10/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html), [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) |
| 6 | Explore the basic concepts of VPC Endpoints and VPC Peering. Compare S3 Gateway Endpoints with Interface Endpoints, and read about costs and data transfer between VPCs. | 09/10/2026 | 09/10/2026 | [S3 Gateway Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html), [VPC Peering](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-peering.html) |
| 7 | Review the week's topics and practice sketching a VPC diagram in draw.io with Public and Private Subnets, Route Tables, and illustrated networking components. Do not deploy EC2 instances, NAT Gateways, or other potentially chargeable resources. | 10/10/2026 | 10/10/2026 | [AWS VPC Examples](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-examples-intro.html) |

### Week 4 Achievements:

**Knowledge Gained:**

- Understood that Amazon VPC is a logically isolated virtual network used to organize resources and manage network connectivity in AWS.
- Learned that a VPC belongs to a Region, while each Subnet is located in one Availability Zone. Became familiar with CIDR notation, such as `10.0.0.0/16` and `10.0.1.0/24`.
- Distinguished Public and Private Subnets based on their Route Tables. Learned that a route to an Internet Gateway alone does not make an EC2 instance accessible from the Internet; a public IP address and appropriate security rules are also needed.
- Understood how NAT Gateways allow resources in Private Subnets to initiate outbound Internet connections.
- Learned that Security Groups are Stateful and support Allow Rules, while Network ACLs are Stateless and support both Allow and Deny Rules at the Subnet level.
- Gained a basic understanding of VPC Peering and VPC Endpoints. Learned that S3 Gateway Endpoints have no additional charge, while Interface Endpoints may incur costs.

**Learning and Practice with the Materials:**

- Reviewed examples of Public and Private Subnets and how traffic is routed using Route Tables.
- Practiced sketching a simple network diagram in draw.io, labeling the main components and connections to better understand how they work together.
- Compared Security Groups and Network ACLs using basic access examples, such as allowing SSH or HTTP traffic.
- Reviewed costs before attempting hands-on activities. Did not create NAT Gateways, Interface Endpoints, EC2 instances, or Public IPv4 addresses during this week's work to avoid unexpected charges.

**Challenges Encountered and Solutions:**

- At first, it was difficult to distinguish Public and Private Subnets because both are part of the same VPC. Reviewing Route Tables and Internet Gateway diagrams helped me better understand how routing determines the Subnet type.
- Security Groups and Network ACLs were easy to confuse because both control network traffic. Comparing Stateful/Stateless behavior and their scope made the differences clearer.
