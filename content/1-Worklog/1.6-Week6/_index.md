---
title: "Week 6 Worklog"
date: 2026-10-19
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

- Learn about Amazon RDS and how AWS supports the management of relational databases.
- Understand the differences between Single-AZ, Multi-AZ DB Instances, and Read Replicas in Amazon RDS.
- Explore Amazon Aurora and its basic architecture, including Writers, Readers, and Cluster Storage.
- Compare SQL and NoSQL databases and learn the fundamental concepts of Amazon DynamoDB.
- Understand Partition Keys, Sort Keys, Query, and Scan operations, while reviewing potential costs before performing practical exercises.
- Continue exploring the LoveSpot project, focusing on organizing restaurant, review, and user information.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about Amazon RDS, DB Instances, and popular database engines such as MySQL and PostgreSQL. Review the relationship between RDS, VPCs, and Security Groups, and explore the main factors affecting costs. | 2026-10-19 | 2026-10-19 | [Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html), [RDS Pricing](https://aws.amazon.com/rds/pricing/) |
| 3 | Study Single-AZ and Multi-AZ DB Instance deployments in RDS. Distinguish Standby instances used for Failover from Read Replicas used for read workloads. Analyze architecture diagrams instead of creating multiple DB Instances. | 2026-10-20 | 2026-10-20 | [RDS Multi-AZ](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html), [RDS Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html) |
| 4 | Learn about Amazon Aurora and its MySQL-compatible and PostgreSQL-compatible editions. Explore an Aurora Cluster with Writers, Readers, and shared Cluster Storage. Study Aurora Serverless and its pricing considerations. | 2026-10-21 | 2026-10-21 | [Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html), [Aurora Pricing](https://aws.amazon.com/rds/aurora/pricing/) |
| 5 | Review basic database concepts and compare SQL with NoSQL. Learn about Amazon DynamoDB, its Key-Value/Document data model, and the concepts of Tables, Items, and Attributes using sample data. | 2026-10-22 | 2026-10-22 | [What Is DynamoDB?](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html), [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| 6 | Study DynamoDB Primary Keys, including Partition Keys and Sort Keys. Practice designing an `Orders` table with `userId` and `orderId` on paper without creating a real AWS table. **Project Work:** Explore how LoveSpot data could be organized, including venue details, reviews, and users, and consider a suitable relational data model. | 2026-10-23 | 2026-10-23 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html), [PostgreSQL Documentation](https://www.postgresql.org/docs/) |
| 7 | Compare Query and Scan operations in DynamoDB. Learn about On-Demand and Provisioned Capacity, review Free Tier conditions, and summarize the differences between RDS, Aurora, and DynamoDB without deploying billable databases. | 2026-10-24 | 2026-10-24 | [DynamoDB Query](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html), [DynamoDB Scan](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Scan.html), [DynamoDB Pricing](https://aws.amazon.com/dynamodb/pricing/) |

### Week 6 Results:

**Knowledge Gained:**

- Understood that Amazon RDS is a managed service for deploying and operating relational databases, supporting common database engines such as MySQL and PostgreSQL.
- Learned that an RDS DB Instance runs a database and is typically deployed within a VPC to manage network connectivity, connecting this knowledge with VPC and Security Group concepts from Week 4.
- Distinguished Single-AZ deployments from Multi-AZ DB Instance deployments with a Standby in another Availability Zone. Understood that this type of Standby supports availability and automatic Failover rather than regular read queries.
- Learned how Read Replicas can distribute read workloads away from the primary database and understood the difference between Read Scaling and High Availability.
- Became familiar with Amazon Aurora, a MySQL-compatible and PostgreSQL-compatible database engine that uses a Cluster architecture with Writers, Readers, and shared storage.
- Understood that DynamoDB is a fully managed NoSQL database service. Learned about Tables, Items, Attributes, and the differences between a Primary Key consisting only of a Partition Key and a composite Primary Key containing both a Partition Key and Sort Key.
- Learned that Query retrieves data using a Partition Key value, optionally with Sort Key conditions, while Scan reads Items from a table or index. Understood that these operations have different resource consumption characteristics.

**Learning Activities and Practice:**

- Analyzed Single-AZ, Multi-AZ DB Instance, and Read Replica architecture diagrams to understand their different purposes.
- Reviewed an Aurora Cluster architecture and identified the roles of Writers, Readers, and Cluster Storage instead of creating a cluster that could incur charges.
- Practiced modeling an `Orders` table using sample data on paper or in notes, with `userId` as the Partition Key and `orderId` as the Sort Key, without creating a DynamoDB table in AWS.
- Created a simple comparison of RDS, Aurora, and DynamoDB based on their database models, data organization, and suitable use cases.
- Reviewed pricing information for RDS, Aurora, and DynamoDB. Learned that DynamoDB provides certain Free Tier allowances for Provisioned Capacity, but that usage limits and billable features must be checked before creating resources.

**LoveSpot Project Activities:**

- Continued exploring how data could be organized for LoveSpot, a restaurant recommendation and itinerary planning application for Ho Chi Minh City.
- Identified important data categories for the application, such as restaurant information, addresses, locations, reviews, and user preferences.
- Explored the use of a relational database such as PostgreSQL for storing and managing application data. Began examining relationships between data categories to support searching and venue recommendations.
- Connected the SQL and NoSQL concepts learned during the week with the project's database requirements, recognizing that database selection should depend on data structure and query patterns. This was an early research and design stage, and the LoveSpot database had not yet been deployed on AWS.

**Challenges Encountered and Solutions:**

- Initially found it difficult to distinguish Multi-AZ Standby instances from Read Replicas because both involve data replication. After comparing architecture diagrams and their intended purposes, I understood that Standby instances in Multi-AZ DB Instance deployments support Failover, while Read Replicas primarily support read scaling.
- Was unfamiliar with DynamoDB data organization because I had mainly worked with SQL table concepts. Creating a simple `Orders` example and defining its Partition Key and Sort Key helped me better understand how DynamoDB identifies and queries Items.