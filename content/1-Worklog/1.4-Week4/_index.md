---
title: "Week 4 Worklog"
date: 2026-10-05
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

- Learn about Amazon VPC and basic networking components in AWS.
- Understand CIDR, Subnets, and the differences between Public and Private Subnets.
- Explore the roles of Route Tables, Internet Gateways, and NAT Gateways.
- Compare Security Groups and Network ACLs in controlling network traffic.
- Gain a basic understanding of VPC Endpoints and VPC Peering, and practice designing a simple VPC diagram.
- Continue exploring the LoveSpot project, focusing on user workflows and the organization of its main components.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about Amazon VPC and the relationship between VPCs, Regions, and Availability Zones. Understand CIDR notation and how IP address ranges are divided into Subnets. | 2026-10-05 | 2026-10-05 | [Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html), [VPC IP Addressing](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-ip-addressing.html) |
| 3 | Study Public Subnets, Private Subnets, Route Tables, and Internet Gateways. Review an example of a `0.0.0.0/0` route pointing to an Internet Gateway. | 2026-10-06 | 2026-10-06 | [Subnet Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/subnet-route-tables.html), [Internet Gateway](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| 4 | Learn how NAT Gateways allow resources in Private Subnets to access the Internet. Review NAT Gateway pricing and analyze architecture diagrams without creating this resource. | 2026-10-07 | 2026-10-07 | [NAT Devices](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat.html), [NAT Gateway Pricing](https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-pricing.html) |
| 5 | Review Security Groups from Week 1 and learn about Network ACLs. Compare their scopes, Allow/Deny Rules, and Stateful/Stateless behavior. | 2026-10-08 | 2026-10-08 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html), [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) |
| 6 | Explore VPC Endpoints and VPC Peering at a basic level. Compare S3 Gateway Endpoints with Interface Endpoints and review potential costs and data transfer considerations between VPCs. | 2026-10-09 | 2026-10-09 | [S3 Gateway Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html), [VPC Peering](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-peering.html) |
| 7 | Review the week's AWS topics and sketch a VPC architecture using draw.io, including Public Subnets, Private Subnets, Route Tables, and network connections. Avoid deploying resources that could incur charges. **Project Work:** Continue exploring LoveSpot and outline the user workflow from searching for places and receiving recommendations to creating an itinerary. | 2026-10-10 | 2026-10-10 | [AWS VPC Examples](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-examples-intro.html) |

### Week 4 Results:

**Knowledge Gained:**

- Understood that Amazon VPC provides a logically isolated virtual network for organizing AWS resources and managing network connectivity.
- Learned that a VPC belongs to a Region, while each Subnet resides in one Availability Zone. Became familiar with CIDR notation, such as `10.0.0.0/16` and `10.0.1.0/24`.
- Distinguished Public Subnets from Private Subnets based on their Route Tables. Understood that a route to an Internet Gateway alone is not sufficient to make an EC2 instance accessible from the Internet; a public IP address and appropriate security rules are also required.
- Learned how NAT Gateways allow resources in Private Subnets to initiate outbound Internet connections.
- Understood that Security Groups are Stateful and support Allow Rules, while Network ACLs are Stateless and support both Allow and Deny Rules at the Subnet level.
- Gained a basic understanding of VPC Peering and VPC Endpoints. Learned that S3 Gateway Endpoints have no additional endpoint charge, while Interface Endpoints may incur costs.

**Learning Activities and Practice:**

- Studied examples showing how Public Subnets, Private Subnets, and network traffic are organized using Route Tables.
- Practiced sketching a simple network architecture using draw.io, labeling components and connections to better understand their roles.
- Compared Security Groups and Network ACLs through basic scenarios, such as allowing SSH or HTTP traffic.
- Reviewed potential AWS costs before performing labs. Did not create NAT Gateways, Interface Endpoints, EC2 instances, or Public IPv4 resources during this week to avoid unexpected charges.

**LoveSpot Project Activities:**

- Continued exploring the development direction of LoveSpot, an application that recommends restaurants and helps users create itineraries in Ho Chi Minh City.
- Outlined a basic user workflow: users provide their preferences or requirements, the system recommends suitable places, and users can organize the recommendations into an itinerary.
- Began identifying the main components of the application, including the user interface, Backend for request processing, and a venue recommendation system.
- Applied the VPC concepts learned during the week to explore how different application components could be separated within a cloud architecture. This was an initial design exploration, and no AWS infrastructure had been deployed for LoveSpot at this stage.

**Challenges Encountered and Solutions:**

- Initially found it difficult to distinguish Public and Private Subnets because both exist within the same VPC. After reviewing Route Tables and Internet Gateway diagrams, I gained a clearer understanding of how routing determines Subnet connectivity.
- Sometimes confused Security Groups with Network ACLs because both control network traffic. Comparing their Stateful/Stateless behavior and scopes helped me understand their differences more clearly.