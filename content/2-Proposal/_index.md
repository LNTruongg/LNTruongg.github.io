
---
title: "Project Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# CoupleLife AI – Intelligent Couple Activity Discovery & Itinerary Planning Platform

## A Platform for Discovering Places and Planning Couple Activities in Ho Chi Minh City

### 1. Overview, Objectives, and Scope

CoupleLife AI is a platform that helps couples discover places, choose activities, and plan outings in Ho Chi Minh City. Users can search for places based on their preferences, discover potential stops along a route, and adjust itineraries according to time, distance, and budget within a single application.

The system consists of a React and Vite frontend, a Backend Gateway, and an AI Service developed with FastAPI. Venue data is combined with routing services and AI models to support searching, ranking, and itinerary recommendations. The system is deployed on AWS in the Singapore Region, using EC2, Amazon RDS for PostgreSQL Multi-AZ, S3, and CloudFront.

**Objectives**

- Build a web application that supports place discovery and itinerary planning based on user needs.
- Combine venue data, route information, and AI to improve the quality of recommendations.
- Design an AWS infrastructure that can maintain service availability when a server fails, manage access, and protect user data.
- Automate testing and deployment, monitor system health, and control operating costs.

**Project Scope**

- Target users: Couples looking for places to visit and planning outings in Ho Chi Minh City.
- Features: POI search, route-based place recommendations, stop management, itinerary optimization, time and budget validation, account authentication, and password recovery via email OTP.
- Infrastructure: Deploy the web application, Backend, AI Service, and database on AWS; use GitHub Actions for CI/CD.
- Initial operating plan: 14 days, with an internal budget of USD 120.

### 2. Problem Statement

**Problem**

When planning an outing, couples often need to consult maps, social media, and review websites to find suitable places. Estimating travel time, balancing the budget, and arranging stops can be time-consuming, especially when an itinerary contains several activities. AI tools may also suggest places that do not match the actual route or available venue data.

**Proposed Solution**

- **POI Discovery:** Search for Points of Interest (POIs) according to user needs and activity categories.
- **Route-Based POI Discovery:** Discover places along the route between an origin and a destination.
- **Hybrid POI Intelligence and Ranking:** Normalize, deduplicate, and rank places by relevance.
- **Itinerary Planning:** Add, remove, and reorder stops, and recalculate routes.
- **Route Optimization:** Optimize the order of stops while preserving the origin and destination.
- **Time & Budget Planning:** Validate time and budget constraints and detect itinerary conflicts.
- **AI Itinerary Refinement:** Suggest itinerary adjustments based on candidate places identified by the system.

**Benefits**

CoupleLife AI brings place discovery, comparison, and planning together in one interface. Users can select places according to their preferences, view routes, and adjust itineraries without manually recalculating each stop. The separation of system components also makes the application easier for the team to maintain and extend in the future.

### 3. Solution Architecture

**Application Architecture**

The frontend collects user input and sends requests to the Backend Gateway. The Backend handles business logic, authentication, account information, and itinerary data, while communicating with the AI Service through an internal Docker network. The AI Service supports POI data processing, place ranking, and itinerary refinement. Application data is stored in PostgreSQL.

The system uses venue data from OpenStreetMap (OSM) and internal sources, OSRM for routing, the Groq API for language models, Cloudflare Workers AI (BGE-M3) for embeddings, and Gmail SMTP for sending email OTPs.

**AWS Architecture**

Users access the website over HTTPS through Amazon CloudFront, with AWS WAF providing edge protection. CloudFront serves static content from a private S3 bucket through Origin Access Control (OAC) and forwards API requests to an Application Load Balancer (ALB). The ALB distributes requests to Backend instances running on two EC2 instances within an Auto Scaling Group. Each EC2 instance runs the Backend and AI Service as Docker containers.

The VPC is divided into six subnets across two Availability Zones in the Singapore Region. Two NAT Gateways provide outbound Internet connectivity for servers in the private application subnets. Both Backend instances access Amazon RDS for PostgreSQL through the same endpoint; the standby database is synchronized to support failover. The website uses the default CloudFront domain name. The connection from CloudFront to the ALB uses HTTP.

**AWS Services Used**

| Service | Purpose |
|---|---|
| Amazon VPC, NAT Gateway, Internet Gateway, S3 Gateway Endpoint | Segment the network and manage connectivity between resources. |
| Amazon CloudFront, AWS WAF, Amazon S3 | Deliver the frontend, protect the edge, and store static content. |
| Application Load Balancer, Amazon EC2, Auto Scaling Group | Distribute traffic and maintain application servers across two Availability Zones. |
| Amazon RDS for PostgreSQL Multi-AZ | Store application data and support failover. |
| Amazon ECR | Store Docker images for the Backend and AI Service. |
| AWS IAM, Secrets Manager, Systems Manager | Manage permissions, credentials, and deployments on EC2. |
| Amazon CloudWatch, Amazon SNS, AWS CloudTrail Event History | Monitor resources, send alerts, and review administrative activities. |
| AWS Budgets, Cost Explorer | Monitor budgets and usage costs. |

GitHub Actions authenticates with AWS through IAM OIDC to run CI/CD. The pipeline tests the application, pushes Docker images to ECR, updates S3 and CloudFront, performs migrations, and updates the EC2 instances one at a time through Systems Manager. Health checks and rollback procedures help reduce interruptions during new releases.

**AWS Well-Architected Framework**

| Pillar | Design Choice |
|---|---|
| Operational Excellence | Automate CI/CD, monitor with CloudWatch, and update application servers sequentially. |
| Security | Use private subnets, WAF, S3 OAC, IAM OIDC, Secrets Manager, and HTTPS at CloudFront. |
| Reliability | Use two Availability Zones, ALB health checks, an Auto Scaling Group, and RDS Multi-AZ. |
| Performance Efficiency | Use the CloudFront CDN, traffic distribution through the ALB, and external AI APIs. |
| Cost Optimization | Prepare cost estimates, use AWS Budgets and an S3 Gateway Endpoint, and clean up resources. |
| Sustainability | Run both containers on EC2, choose instance sizes based on demand, and release unused resources. |

Reference: [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html).

### 4. Technical Implementation

**Implementation Phases**

The team develops the application in phases, starting with the Backend foundation, venue data, and routing, then completing ranking and itinerary optimization.

**Phase 1 – Backend Safety & Configuration**

- **1.1 – Test Database Isolation:** Ensure that the test database environment is isolated.
- **1.2 – Production SECRET_KEY:** Standardize the SECRET_KEY configuration for the production environment.
- **1.3 – AI Configuration:** Standardize connectivity settings and AI provider management.

**Phase 2 – Routing & Application Integration**

- **2.1 – POI & Google Maps Investigation:** Examine POI data and the Google Maps integration process.
- **2.2 – Fix POI Data Integrity:** Address venue data integrity issues.
- **2.3a – Google Maps Navigation Accuracy:** Improve the accuracy of generated navigation links.
- **2.3b – Routing Service A → B:** Build a routing service between the origin and destination.
- **2.4 – A/B Coordinate Standardization:** Standardize the state and coordinates of the two route endpoints in the frontend.
- **2.5 – Connect Planner A/B to the Routing Service:** Integrate the planning interface with the Routing API.
- **2.6 – Route-Based POI Discovery:** Build functionality to discover POIs along a route.

**Task 2.8 – Route-Based Itinerary Planning**

- **2.8.3 – Routing Engine:** Build and integrate the routing engine.
- **2.8.4 – Route-Based POI Discovery:** Search for places within a route corridor.
- **2.8.5 – Frontend API Integration:** Connect the frontend with the discovery and routing APIs.
- **2.8.6 – Ranked POI Results UI:** Build the interface for displaying ranked POI results.
- **2.8.7 – POI Selection & Stop Management:** Manage the selection, addition, and removal of stops.
- **2.8.8 – Itinerary Construction:** Construct an itinerary from point A through selected POIs to point B.
- **2.8.9 – Multi-Waypoint Routing:** Integrate routing through multiple stops.
- **2.8.10 – Route Optimization:** Optimize the order of stops.
- **2.8.11 – Time & Budget Planning:** Validate itinerary time and budget constraints.
- **2.8.12 – AI Itinerary Refinement:** Integrate AI to suggest itinerary refinements.

**Phase 3 – Route-Based POI Discovery Foundation**

- **3.1–3.10 – Route-Based POI Discovery Implementation:** Build and complete the components for route-based POI discovery.
- **3.11 – Route POI Discovery Audit:** Review category filtering and duplicate-handling issues.
- **3.12 – Route POI Discovery Corrections:** Fix POI category normalization and deduplication issues.
- **3.13 – Top 50 POI Selection Audit:** Review the selection rules and limits for candidate places.

Related frontend and integration tasks include:

- Route Location Input.
- Route State & Coordinate Management.
- Routing API Integration.
- Route Map Display.
- Route POI Results Display.
- POI Marker & Card Synchronization.
- Add/Remove POI from Itinerary.
- Route Stops Management.
- Multi-Waypoint Route Recalculation.
- Origin/Destination Change Handling.
- Stale Request Protection.

**Phase 4 – Google Places Identity Resolution**

- **4.1 – Architecture Audit:** Review the current place identity architecture.
- **4.2 – API & Identity Specification:** Define specifications for Google Places API integration and identity data.
- **4.3 – Minimal Google Places Identity Resolution Implementation:** Integrate Google Places on the server side, search for places, and handle matching.
- **4.4 – Verification & Closure:** Test and complete the place identity integration.

**Phase 5 – Hybrid POI Intelligence & Ranking**

- **5.1 – POI Intelligence Architecture Audit:** Review the POI processing and ranking architecture.
- **5.2 – Category Canonicalization & Intent Relevance:** Normalize categories and determine their relevance to the intended trip.
- **5.3 – Scheduler-Owned Budget & Opening Hours:** Validate budgets and opening hours during itinerary scheduling.
- **5.4 – Ranking-to-Itinerary Regression:** Run regression tests for ranking, POI selection, and itinerary construction.

**Phase 6 – Itinerary Optimization**

- **6.1 – Itinerary Optimization Foundation:** Build the itinerary optimization foundation.
- Selected Stop Ordering: Determine the order of selected stops.
- Manual Stop Ordering: Allow users to manually reorder stops.
- Drag-and-Drop Reordering: Support dragging and dropping stops to change their order.
- Keyboard Reordering: Support changing stop order using the keyboard.
- Origin & Destination Preservation: Preserve the origin and destination.
- Intermediate Stop Optimization: Optimize intermediate stops.
- Route Progress Ordering: Order stops according to progress along the route.
- Two-Opt Optimization: Apply the two-opt algorithm to optimize stop order.
- Multi-Waypoint Routing Integration: Integrate multi-stop routing.
- Itinerary Schedule Validation: Validate itinerary schedules.
- Conflict Detection: Detect itinerary conflicts.
- Conflict Resolution Proposals: Suggest ways to resolve conflicts.
- Accept/Reject Proposals: Allow users to accept or reject suggestions.
- Stale Revision Protection: Prevent changes based on outdated itinerary revisions.
- Route & Map Synchronization: Keep stop order, routes, and the map synchronized.
- Itinerary UI Integration: Integrate itinerary management features into the interface.

**Finalization and AWS Deployment Phase**

After Phases 1–6, the team continues with the following tasks:

- Final Validation & Release Gate: Test main user flows, invalid inputs, provider failures, regressions, and builds.
- Security Hardening: Finalize production settings, secrets management, and safe logging practices.
- Authentication Foundation: Finalize Backend authentication and session management.
- Authentication & Data Layer: Integrate the Backend JWT/session mechanism with PostgreSQL.
- AWS Deployment: Package Docker containers and configure networking, databases, EC2, and supporting services.
- CI/CD & Validation: Automate testing, migrations, rolling deployments, and application validation on AWS; integrate password recovery via email OTP.

**Technical Requirements**

- **Frontend:** React, Vite, TypeScript, state management, and API integration.
- **Backend:** Python, FastAPI, Pydantic, REST APIs, JWT/session, and internal authentication.
- **AI Service:** Python, FastAPI, POI data processing, ranking, and AI itinerary refinement.
- **POI Data:** OpenStreetMap, Overpass API during development, and internal venue data.
- **Routing:** OSRM, GeoJSON, and geographic coordinates.
- **Place Identity:** Place IDs and matching mechanisms during place identity development.
- **AI Integration:** Groq API and Cloudflare Workers AI (BGE-M3).
- **Email:** Gmail SMTP for password recovery via OTP.
- **Storage:** PostgreSQL, Alembic migrations, and Amazon RDS for the AWS environment.
- **Deployment:** Docker, EC2, Auto Scaling Group, ECR, S3, CloudFront, Systems Manager, Secrets Manager, and GitHub Actions.

### 5. Roadmap & Milestones

The team completes the application in the local environment before integrating and deploying it on AWS.

**Foundation Development Phase**

- **Phases 1–3:** Complete the Backend foundation, POI data, routing, route-based place discovery, and related frontend workflows.
- **Phase 4:** Integrate Google Places Identity Resolution during development.
- **Phase 5:** Complete Hybrid POI Intelligence and Ranking.
- **Phase 6:** Complete Itinerary Optimization and itinerary management features.

**Testing and Security Phase**

- Complete the Final Validation & Release Gate.
- Test POI search, routing, stop selection, and itinerary optimization.
- Check data errors, connection failures, and external provider errors.
- Finalize security and production configuration.

**AWS Integration Phase**

- **Step 1 – Authentication Foundation:** Finalize authentication and session management.
- **Step 2 – Authentication Integration:** Connect the Backend authentication mechanism to the frontend.
- **Step 3 – Data Layer:** Prepare PostgreSQL, migrations, and application data.
- **Step 4 – Local Integration Testing:** Test functionality with local configuration.
- **Step 5 – AWS Infrastructure:** Set up networking, databases, EC2, containers, frontend delivery, and secrets management.
- **Step 6 – Deployment & Validation:** Deploy to AWS, complete CI/CD, verify real-world operation, and monitor costs.

**Operations Phase:** Keep the system running for 14 days, monitor application health and costs, then back up any necessary data and clean up resources.

### 6. Budget Estimate

The estimate was prepared using AWS Pricing Calculator for the Singapore Region, with two `t3.small` EC2 instances (20 GiB gp3 per instance), Amazon RDS for PostgreSQL `db.t3.micro` Multi-AZ (20 GiB gp3), two NAT Gateways, and one ALB. The estimated operating time is 730 hours per month.

| Service | Estimated Cost (USD/month) |
|---|---:|
| VPC, NAT Gateway, and public IPv4 | 101.32 |
| Amazon RDS for PostgreSQL | 46.40 |
| Amazon EC2 and EBS | 42.38 |
| Application Load Balancer | 24.24 |
| AWS WAF | 7.60 |
| AWS Secrets Manager | 1.70 |
| Amazon ECR | 0.10 |
| Amazon S3 | 0.03 |
| Amazon SNS | 0.00 |
| Amazon CloudFront | 0.00 |
| **Total** | **223.77** |

[CoupleLife AI estimate on AWS Pricing Calculator](https://calculator.aws/#/estimate?id=01ec0aee30504f4a008d08d0db765ffb13d06485).

| Item | Amount (USD) |
|---|---:|
| Estimated cost for 14 days (336 hours) | 103.00 |
| Internal budget | 120.00 |
| Contingency | 17.00 |

The team plans to use AWS Promotional Credits with a limit of USD 200, subject to the account's eligibility and conditions. These estimates are calculated before credits and taxes, based on assumed configurations and traffic. Actual costs may vary depending on operating time, network traffic, API requests, and monitoring service usage.

**Cost Optimization Measures**

- Use CloudFront to cache static content and an S3 Gateway Endpoint to reduce S3 traffic through NAT Gateways.
- Run the Backend and AI Service together on each EC2 instance, using external AI APIs within free usage limits instead of GPU servers.
- Keep two NAT Gateways and RDS Multi-AZ to maintain system availability.
- Monitor Cost Explorer, Bills, and remaining credits; configure AWS Budgets alerts at 50%, 80%, and 100% of the budget.
- Clean up resources at the end of the operating period to avoid additional charges.

### 7. Risk Assessment

| Risk | Impact | Likelihood | Mitigation |
|---|---|---|---|
| Missing, inaccurate, or duplicate POI data | High | Medium | Normalize, deduplicate, and validate venue data. |
| External routing or AI service failure, or exceeded quotas | High | Medium | Limit requests and timeouts; use available data or fallbacks where supported. |
| Itinerary exceeding the budget or containing scheduling conflicts | Medium | Medium | Validate constraints before applying suggestions. |
| Exposed credentials or unauthorized access | High | Medium | Use Secrets Manager, least-privilege IAM, Backend authentication, and session protection. |
| HTTP connection to the ALB origin | High | Medium | Restrict origin access; consider HTTPS between CloudFront and ALB when expanding the system. |
| Server or database failure | High | Low to Medium | Use two Availability Zones, ALB health checks, ASG, RDS Multi-AZ, and backups. |
| Deployment or migration errors | High | Medium | Test changes, verify schema compatibility, perform rolling deployments, and roll back images. |
| Alerts not reaching recipients | Medium | Medium | Confirm SNS email subscriptions and verify that alerts are received. |
| AWS costs exceeding the budget | High | Medium | Set budget alerts, monitor daily costs, and clean up resources on schedule. |

**Contingency Plan**

When external services are unavailable, the system reports the error and uses fallback mechanisms for features that support them. If a new release fails, the previous Docker image is restored after checking database compatibility. If RDS encounters a failure, failover or backup recovery is used. When costs are at risk of exceeding the budget, the team reviews usage, stops unnecessary resources, and backs up data before cleanup.

### 8. Expected Outcomes

**Technical Outcomes**

- Complete a web application for discovering places, routing through multiple stops, and planning itineraries based on preferences, time, and budget.
- Use real venue data to rank and recommend relevant stops.
- Deploy the application on AWS with two EC2 instances in two Availability Zones and Amazon RDS for PostgreSQL Multi-AZ.
- Complete CI/CD, application health checks, account authentication, and password recovery via email OTP.
- Set up resource monitoring, budget alerts, and a cleanup procedure for the end of the operating period.

**Long-term Value**

CoupleLife AI provides a foundation for adding personalized features, saving trip history, and expanding venue data to other areas. Separating the frontend, business logic, and AI components makes the system easier to maintain and scale.
