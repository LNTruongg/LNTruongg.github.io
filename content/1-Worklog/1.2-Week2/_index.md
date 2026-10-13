---
title: "Week 2 Worklog"
date: 2026-09-22
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives

- Gain a deeper understanding of Amazon EC2, its pricing models, and Amazon EBS storage services.
- Practice managing disk storage capacity on an EC2 Windows Server instance.
- Understand how to manage AWS resources.
- Install and become familiar with AWS CLI to interact with AWS services through the command line.
- Learn about Amazon S3 and practice basic data storage operations.

### Tasks Completed During the Week

| Day | Task | Start Date | Completion Date | References |
|---|---|---|---|---|
| Tuesday | Visited the AWS office, explored the working environment, and met the mentors and other class members. | 2026-09-22 | 2026-09-22 | AWS Office |
| Wednesday | Studied EC2 pricing, use cases, and commonly used EBS volume types. Practiced attaching an additional EBS volume to an EC2 Windows Server instance, initializing and mounting the disk, creating text files, and modifying the volume size through the AWS Management Console. | 2026-09-23 | 2026-09-23 | [AWS EC2 Tutorial](https://www.youtube.com/watch?v=ILQeF7Z-Sis) |
| Thursday | Checked and terminated EC2 instances created during practice to avoid additional charges. Learned more about AWS resource management. | 2026-09-24 | 2026-09-24 | [AWS Roadmap](https://roadmap.sh/aws), [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Friday | Installed AWS CLI on a personal computer, checked its version, and learned how to configure AWS CLI using access keys. Read introductory documentation about Amazon S3. | 2026-09-25 | 2026-09-25 | [AWS CLI Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) |
| Saturday | Studied the concepts, features, and use cases of Amazon S3. Practiced creating an S3 bucket and folders, as well as uploading, downloading, and deleting files. | 2026-09-26 | 2026-09-26 | [AWS Roadmap](https://roadmap.sh/aws), [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |

### Week 2 Achievements

#### Knowledge Acquired

- EC2 pricing models and Amazon EC2 use cases.
- Amazon EBS volume types and storage capacity management.
- EC2 instance lifecycle management and AWS cost control.
- Basic AWS CLI installation and configuration.
- Amazon S3 concepts, including buckets, objects, and basic storage operations.

#### Hands-on Practice with Amazon EC2 and EBS

- Explored EC2 pricing models and common EBS volume types.
- Attached an additional EBS volume to an EC2 Windows Server instance.
- Initialized and mounted a new disk on Windows Server.
- Created and managed text files on the disk.
- Practiced modifying EBS volume capacity through the AWS Management Console.
- Learned how to expand storage capacity when a server runs low on disk space without recreating the EC2 instance.

#### AWS Resource and Cost Management

- Recorded approximately USD 3.20 in charges incurred during EC2 experiments.
- Terminated EC2 instances that were no longer needed.
- Recognized the importance of regularly checking AWS resources and monitoring costs.

#### AWS CLI Installation and Exploration

- Installed AWS CLI on a personal computer.
- Learned how to check the installed AWS CLI version.
- Explored how to use access keys to configure authentication credentials for AWS CLI.

#### Hands-on Practice with Amazon S3

- Understood that Amazon S3 is an object storage service provided by AWS.
- Created an S3 bucket.
- Created folders and uploaded files to S3.
- Downloaded files from S3 to a local computer.
- Deleted files stored in S3.
- Learned about S3 use cases for storing different types of data.

#### Challenges Encountered

- The EC2 Windows Server instance responded relatively slowly, making hands-on tasks more difficult.
- Uploading multiple files to S3 at once took considerable time, so most files were uploaded individually.
- EC2 experiments incurred charges, highlighting the need to regularly monitor AWS resources and costs.
