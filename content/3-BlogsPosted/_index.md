
---
title: "Published Blog Posts"
date: 2026-11-17
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Throughout my journey of learning and exploring Amazon Web Services (AWS), I have written and shared technical articles analyzing real-world scenarios that developers and cloud engineers may encounter when building, operating, and securing cloud-based systems.

Below are three blog posts I have published, focusing on how AWS services work, commonly overlooked issues, and practical solutions.

### [Blog 1 - AWS LAMBDA + SQS: WHY CAN ONE FAILED MESSAGE CAUSE AN ENTIRE BATCH TO BE PROCESSED AGAIN?](3.1-Blog1/)

This article explores batch message processing when integrating **AWS Lambda** with **Amazon SQS**. By default, if a single message fails during processing, the entire batch may become available for reprocessing, potentially resulting in duplicate processing of messages that have already succeeded.

The article also introduces **Partial Batch Response**, **Idempotency**, and important practices for building more reliable message-processing systems.

**[Read the original post on Facebook](https://www.facebook.com/share/p/1C8K1bvGzK/)**

### [Blog 2 - AMAZON S3: WHY CAN STORAGE COSTS CONTINUE EVEN AFTER DELETING FILES?](3.2-Blog2/)

This article examines how **S3 Versioning** and **Lifecycle Rules** interact. When Versioning is enabled, deleting an object may only create a Delete Marker, while previous object versions remain stored and continue to incur storage costs.

It explains the roles of **Delete Markers** and **Noncurrent Versions**, as well as how to configure Lifecycle rules appropriately to manage data and optimize Amazon S3 storage costs.

**[Read the original post on Facebook](https://www.facebook.com/share/p/18Z3mD7KML/)**

### [Blog 3 - AWS API GATEWAY: HOW CAN CACHING AN ALLOW RESPONSE UNINTENTIONALLY GRANT ACCESS TO ANOTHER ROUTE?](3.3-Blog3/)

This article analyzes an authorization risk involving **Amazon API Gateway HTTP API**, **Lambda Authorizers**, **Simple Responses**, and **Authorizer Caching**.

If the cache key is based only on user identity without distinguishing between routes, an `Allow` result from one route may be reused for another route, potentially granting unintended access.

The article explains the underlying caching mechanism and possible mitigations, such as including `$context.routeKey` in the Identity Sources or designing appropriate route-specific authorization policies.

**[Read the original post on Facebook](https://www.facebook.com/share/p/1BPEBPipns/)**
