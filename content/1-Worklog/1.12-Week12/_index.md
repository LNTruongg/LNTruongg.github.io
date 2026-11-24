---
title: "Worklog Week 12"
date: 2026-11-30
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

- Learn about Infrastructure as Code (IaC) and how AWS CloudFormation supports infrastructure management through configuration files.
- Become familiar with CloudFormation Templates, Stacks, and basic components such as Resources, Parameters, and Outputs.
- Understand the importance of Backup & Recovery, AWS Backup, and the concepts of RPO and RTO.
- Review the key AWS concepts covered throughout the learning program.
- **Project Work:** Continue improving the restaurant recommendation and itinerary planning application for Ho Chi Minh City.
- **Project Work:** Test the complete workflow from user inputs to restaurant recommendations and generated itineraries.
- **Project Work:** Review restaurant data, improve recommendation quality, and evaluate the user experience.
- **Project Work:** Prepare a demonstration, summarize the results, and identify remaining limitations.

### Tasks to Complete This Week:

| Day | Task | Start Date | Completion Date | References |
| --- | --- | --- | --- | --- |
| Monday | Learn about Infrastructure as Code (IaC) and AWS CloudFormation. Explore Templates, Stacks, and YAML sections such as Resources, Parameters, and Outputs. Review examples of managing AWS resources through Templates instead of manual configuration, without creating an actual Stack. | 30/11/2026 | 30/11/2026 | [AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html), [CloudFormation Template Sections](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html) |
| Tuesday | Learn about Backup & Recovery, AWS Backup, and backup methods such as EBS Snapshots and RDS Backups. Understand the differences between RPO and RTO through data loss and system outage scenarios. Review AWS concepts and potential costs without creating actual backup resources. | 01/12/2026 | 01/12/2026 | [AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/whatisbackup.html), [Amazon RDS Backup](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.BackupRestore.html), [Disaster Recovery Objectives](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/disaster-recovery-dr-objectives.html) |
| Wednesday | **Project Work:** Review the overall workflow of the restaurant recommendation and itinerary planning application for Ho Chi Minh City. Examine how user inputs, including budget, food preferences, location, and available time, are processed to generate restaurant recommendations and itineraries. | 02/12/2026 | 02/12/2026 | Project Frontend, Backend, and recommendation system source code |
| Thursday | **Project Work:** Evaluate restaurant data quality and recommendation results. Review cases involving missing GPS coordinates, invalid information, restaurants outside the user's budget, or excessive travel distances. Examine how destinations are selected and ordered within generated itineraries. | 03/12/2026 | 03/12/2026 | Restaurant dataset, data processing documentation, and test scenarios |
| Friday | **Project Work:** Test the integration between the Frontend, Backend, and recommendation system. Check how restaurant information, itineraries, and maps are displayed. Review invalid inputs, situations with no suitable restaurants, and API errors to identify possible user experience improvements. | 04/12/2026 | 04/12/2026 | Project source code, APIs, and testing documentation |
| Saturday | **Project Work:** Prepare and test a local demonstration of the application. Review its main features, summarize testing results, and document remaining issues. Review project presentation materials and identify tasks for further development after this stage. | 05/12/2026 | 05/12/2026 | Project source code, documentation, and demo testing checklist |

### Expected Outcomes for Week 12:

**AWS Knowledge Acquired:**

- Understand Infrastructure as Code (IaC) as an approach to managing infrastructure through code and configuration files rather than relying entirely on manual operations.
- Understand how AWS CloudFormation uses Templates to describe resources and Stacks to manage deployed resources.
- Become familiar with YAML structures and the Resources, Parameters, and Outputs sections.
- Understand the importance of Backup & Recovery in reducing the risk of data loss and minimizing service interruptions.
- Recognize how AWS Backup supports centralized backup management for supported AWS resources.
- Distinguish between RPO, the acceptable amount of data loss measured in time, and RTO, the maximum acceptable time required to restore a system.
- Review the AWS knowledge acquired throughout the learning program and understand the importance of selecting services according to actual requirements and costs.

**Expected Project Outcomes:**

- **Project Work:** Evaluate the application's main workflow from user inputs to restaurant recommendations and itinerary generation.
- **Project Work:** Identify invalid restaurant data that may affect recommendation results and map visualization.
- **Project Work:** Assess restaurant suitability based on user preferences, budget, geographical location, and travel distance.
- **Project Work:** Review data exchange between the Frontend, Backend, and recommendation system while documenting integration issues discovered during testing.
- **Project Work:** Test the application's main features and improve user experience issues within the available development time.
- **Project Work:** Prepare a local demonstration to present the application's objectives, usage, and completed features.
- **Project Work:** Summarize project achievements, remaining limitations, and possible directions for future development.

**Challenges and Proposed Solutions:**

- **AWS Knowledge:** CloudFormation and AWS Backup involve several infrastructure-related concepts. Focus on understanding the fundamentals, reviewing examples, and controlling costs rather than creating unnecessary AWS resources.
- **Project Work — Data Quality:** Restaurant records with missing or inaccurate GPS coordinates may affect distance calculations and map visualization. Validate location data before using it.
- **Project Work — Itinerary Quality:** Recommended destinations should match user requirements and follow a reasonable travel order rather than relying only on restaurant ratings.
- **Project Work — System Integration:** Ensure consistent data structures between the Frontend, Backend, and recommendation system to reduce processing and integration errors.
- **Project Work — User Experience:** Handle incomplete inputs, unavailable restaurants, and recommendation results that do not satisfy user constraints appropriately.
- **Project Work — Demo Preparation:** Prioritize testing core features and clearly distinguish completed functionality from features that are still under development.
- **Project Work — Deployment:** Focus on local development and testing. Consider AWS deployment separately based on technical requirements and estimated costs.
