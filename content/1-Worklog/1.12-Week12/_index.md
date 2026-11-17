---
title: "Week 12 Worklog"
date: 2026-11-30
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

- Learn about Infrastructure as Code (IaC) and how AWS CloudFormation helps manage infrastructure.
- Become familiar with CloudFormation Templates, Stacks, and basic YAML sections.
- Understand the importance of Backup & Recovery and the concepts of RPO and RTO.
- Explore AWS Backup and review the AWS topics covered during the 12 weeks.

### Tasks to Be Completed This Week:

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 2 | Learn about Infrastructure as Code (IaC) and AWS CloudFormation. Review an example of using a Template to manage resources instead of creating them one by one. | 30/11/2026 | 30/11/2026 | [AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) |
| 3 | Learn about CloudFormation Templates and Stacks. Explore YAML and basic sections such as Resources, Parameters, and Outputs; read examples without creating a Stack. | 01/12/2026 | 01/12/2026 | [CloudFormation Template Sections](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html) |
| 4 | Learn why data backups are important. Review examples of EBS Snapshots and RDS backups to understand how data can be recovered after a problem. | 02/12/2026 | 02/12/2026 | [Amazon EBS Snapshots](https://docs.aws.amazon.com/ebs/latest/userguide/ebs-snapshots.html), [Amazon RDS Backup](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.BackupRestore.html) |
| 5 | Learn about AWS Backup, Backup Plans, Backup Vaults, and backup retention. Read about backup storage costs without creating a real Backup Plan or Snapshot. | 03/12/2026 | 03/12/2026 | [AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html), [Backup Plans](https://docs.aws.amazon.com/aws-backup/latest/devguide/about-backup-plans.html) |
| 6 | Learn about RPO and RTO through an example of a website losing data or becoming unavailable. Read how these goals affect Backup & Recovery planning. | 04/12/2026 | 04/12/2026 | [Disaster Recovery Objectives](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/disaster-recovery-dr-objectives.html) |
| 7 | Review the topics learned, from EC2, S3, and VPC to Lambda, Databases, and Monitoring. Go over any unclear concepts and check CloudFormation and AWS Backup pricing without creating new resources. | 05/12/2026 | 05/12/2026 | [CloudFormation Pricing](https://aws.amazon.com/cloudformation/pricing/), [AWS Backup Pricing](https://aws.amazon.com/backup/pricing/) |

### Expected Week 12 Achievements:

**Knowledge to Gain:**

- Understand that IaC manages infrastructure through configuration files instead of doing everything manually, and that CloudFormation uses Templates to create and manage AWS resources.
- Learn that a Template describes the resources, while a Stack is a group of resources managed by CloudFormation. Become familiar with Resources, Parameters, and Outputs in YAML.
- Understand that backups reduce the risk of data loss, and that Snapshots and database backups are common ways to protect data.
- Learn that AWS Backup helps manage backups in one place using Backup Plans and Backup Vaults.
- Understand that RPO is the acceptable amount of data loss, while RTO is the maximum acceptable time to restore a system.

**Review and Learning with the Materials:**

- Read a sample CloudFormation Template to identify its main sections without creating a Stack or EC2 instance.
- Review EC2 and RDS backup examples and the difference between backing up and restoring data.
- Review the AWS topics covered during the 12 weeks and check pricing. Do not create Snapshots or use AWS Backup to avoid extra storage costs.

**Topics to Watch Out For and How to Study Them:**

- CloudFormation YAML can look complicated because it has several sections. Starting with a short Template and focusing on Resources before Parameters and Outputs can make it easier to understand.
- RPO and RTO both relate to recovery, but a simple example helps: RPO is about how much data can be lost, while RTO is about how long a system can be unavailable.