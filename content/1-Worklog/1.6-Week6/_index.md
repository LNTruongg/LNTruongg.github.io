
---
title: "Week 6 Worklog"
date: 2026-10-19
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

- Learn about Amazon RDS and how AWS helps manage relational databases.
- Understand the differences between Single-AZ, Multi-AZ DB Instance deployments, and RDS Read Replicas.
- Become familiar with Amazon Aurora and a basic architecture with Writers, Readers, and Cluster Storage.
- Compare SQL and NoSQL databases and learn the basic concepts of Amazon DynamoDB.
- Explore Partition Keys, Sort Keys, Query, and Scan, while reviewing costs before attempting hands-on practice.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Amazon RDS, DB Instances, and common database engines such as MySQL and PostgreSQL. Review how RDS relates to VPCs and Security Groups, and read about the main factors affecting database costs. | 19/10/2026 | 19/10/2026 | [Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html), [RDS Pricing](https://aws.amazon.com/rds/pricing/) |
| 3 | Learn about Single-AZ and Multi-AZ DB Instance deployments in RDS. Compare a Standby instance used for Failover with a Read Replica used for read traffic; analyze diagrams instead of launching multiple DB Instances. | 20/10/2026 | 20/10/2026 | [RDS Multi-AZ](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html), [RDS Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html) |
| 4 | Learn about Amazon Aurora and its MySQL- and PostgreSQL-compatible editions. Review an Aurora Cluster with a Writer, Readers, and shared storage; explore the basic idea of Aurora Serverless and its costs. | 21/10/2026 | 21/10/2026 | [Amazon Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html), [Aurora Pricing](https://aws.amazon.com/rds/aurora/pricing/) |
| 5 | Review basic database concepts and compare SQL with NoSQL. Learn about Amazon DynamoDB, Key-Value/Document models, and the Table, Item, and Attribute concepts using sample data. | 22/10/2026 | 22/10/2026 | [What Is DynamoDB?](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html), [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| 6 | Learn about DynamoDB Primary Keys, including Partition Keys and Sort Keys. Practice designing a simple `Orders` table on paper with `userId` and `orderId`, without creating a real table on AWS. | 23/10/2026 | 23/10/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| 7 | Learn the difference between Query and Scan in DynamoDB. Read about On-Demand and Provisioned Capacity, check Free Tier conditions, and review RDS, Aurora, and DynamoDB in a comparison table without deploying chargeable databases. | 24/10/2026 | 24/10/2026 | [DynamoDB Query](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html), [DynamoDB Scan](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Scan.html), [DynamoDB Pricing](https://aws.amazon.com/dynamodb/pricing/) |

### Week 6 Achievements:

**Knowledge Gained:**

- Understood that Amazon RDS is a managed service for relational databases and supports familiar database engines such as MySQL and PostgreSQL.
- Learned that an RDS DB Instance runs a database and is typically placed inside a VPC to manage network access, connecting this topic to the VPC and Security Group concepts from Week 4.
- Distinguished Single-AZ from a Multi-AZ DB Instance deployment with one Standby in another Availability Zone. Understood that this Standby provides high availability and automatic Failover rather than serving normal read queries.
- Understood that a Read Replica helps handle read traffic separately from the primary database, and learned the difference between Read Scaling and High Availability.
- Learned that Amazon Aurora is compatible with MySQL/PostgreSQL and uses a Cluster architecture with a Writer, Readers, and shared storage.
- Understood that DynamoDB is a fully managed NoSQL database. Became familiar with Tables, Items, Attributes, and the difference between a Primary Key using only a Partition Key and one combining a Partition Key with a Sort Key.
- Learned that Query retrieves data using a Partition Key value, while Scan examines Items in a table or Index, and that these operations have different resource usage characteristics.

**Learning and Practice with the Materials:**

- Analyzed Single-AZ, Multi-AZ DB Instance, and Read Replica diagrams to compare when each deployment approach is useful.
- Reviewed an Aurora Cluster diagram to identify the roles of the Writer, Readers, and Cluster Storage instead of creating a potentially chargeable Cluster.
- Practiced modeling a sample `Orders` table on paper or in notes, using `userId` as the Partition Key and `orderId` as the Sort Key, without creating a DynamoDB Table in the AWS account.
- Made a simple comparison of RDS, Aurora, and DynamoDB based on database type, data organization, and common use cases.
- Reviewed pricing information for RDS, Aurora, and DynamoDB. Learned that DynamoDB has a limited free usage allowance with Provisioned Capacity, but account limits and optional paid features still need to be checked before using AWS resources.

**Challenges Encountered and Solutions:**

- At first, Multi-AZ Standby instances and Read Replicas were easy to confuse because both involve data replication. Comparing the diagrams and their purposes helped clarify that the Standby in a Multi-AZ DB Instance deployment is used for Failover, while a Read Replica mainly supports read scaling.
- DynamoDB's data model was unfamiliar because I had mostly worked with SQL-style tables before. Creating a simple `Orders` example and identifying its Partition Key and Sort Key made it easier to understand how DynamoDB identifies and retrieves Items.
