---
title: "Week 3 Worklog"
date: 2026-09-28
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

- Learn how to manage data access permissions in Amazon S3.
- Understand S3 Versioning for storing and recovering different versions of files.
- Explore S3 Storage Classes and how to select the appropriate storage class.
- Learn how to automate data management using S3 Lifecycle.
- Understand how to host a simple static website using Amazon S3.
- Begin exploring the requirements and development direction of the LoveSpot project.

### Tasks to Be Implemented During This Week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | Learn about S3 Bucket Policies and how to manage access permissions for S3 buckets. | 2026-09-28 | 2026-09-28 | [AWS S3 Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) |
| 3 | Study S3 Versioning. Practice enabling Versioning, uploading files, and checking different file versions. | 2026-09-29 | 2026-09-29 | [S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) |
| 4 | Explore S3 Storage Classes and the differences between S3 Standard, Standard-IA, and Glacier. | 2026-09-30 | 2026-09-30 | [S3 Storage Classes](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html) |
| 5 | Learn about S3 Lifecycle and how to automatically transition or delete files after a specified period. | 2026-10-01 | 2026-10-01 | [S3 Lifecycle](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html) |
| 6 | Study S3 Static Website Hosting and practice uploading HTML files to host a static website on S3. | 2026-10-02 | 2026-10-02 | [S3 Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html) |
| 7 | Review the AWS topics covered during the week, check and delete unused AWS resources. Project Work: explore the initial requirements and planned features of LoveSpot. | 2026-10-03 | 2026-10-03 | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |

### Week 3 Results:

**Knowledge Gained:**

- Understood how to manage access permissions for Amazon S3 using Bucket Policies.
- Learned that S3 Versioning can store multiple versions of the same file and support data recovery.
- Identified the differences between several S3 Storage Classes, including Standard, Standard-IA, and Glacier.
- Understood how S3 Lifecycle can automatically transition objects between storage classes or delete them based on defined rules.
- Learned that Amazon S3 can be used to store and serve static website files.

**Practical Exercises:**

- Enabled S3 Versioning, uploaded files, and examined different file versions.
- Created an S3 Lifecycle Rule to manage how long files are stored.
- Uploaded HTML files to Amazon S3 and explored Static Website Hosting configuration.
- Checked and deleted unused AWS resources to avoid unnecessary costs.

**LoveSpot Project Activities:**

- Began exploring the idea of developing LoveSpot, an application that recommends restaurants and helps users plan itineraries in Ho Chi Minh City.
- Identified several planned features, including searching for places, providing recommendations based on user preferences, and helping users create itineraries.
- Conducted initial research on how restaurant and venue information could be organized to support the recommendation system in later development stages.

**Challenges Encountered:**

- Spent considerable time understanding S3 Storage Classes because they offer different features and pricing models.
- Initially encountered difficulties accessing the website during the S3 Static Website Hosting exercise due to incorrectly configured bucket access permissions.
- For LoveSpot, further research was needed to determine how venue data should be organized and to define an appropriate feature scope before developing the main system components.