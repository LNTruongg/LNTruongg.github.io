---
title: "Set up AWS infrastructure"
date: 2026-11-27
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

This section prepares networking, access permissions and the database before starting containers. Separating public, application and database subnets limits access instead of exposing the entire application to the Internet.

Follow VPC → Security Groups/IAM → RDS. The two application secrets depend on database and application configuration, so return to section 5.3.2 to finish them before launching EC2.

#### Contents

1. [VPC and networking](5.3.1-VPC-Networking/)
2. [Security groups and IAM](5.3.2-Security-IAM/)
3. [Amazon RDS for PostgreSQL](5.3.3-RDS-PostgreSQL/)
