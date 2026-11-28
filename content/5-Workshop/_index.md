---
title: "Workshop"
date: 2026-11-27
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Deploy CoupleLife AI on AWS

#### Overview

Planning a date in Ho Chi Minh City often means switching between restaurant listings, maps and travel estimates. CoupleLife AI brings these tasks together in a website. Users enter a starting point, destination, budget and preferences, then explore places along the route and arrange an itinerary.

In this workshop, we deploy the React/Vite frontend and two FastAPI services to AWS in Singapore. S3 hosts the frontend assets, CloudFront distributes them, and two EC2 instances in an Auto Scaling group run the backend and AI service against a shared Multi-AZ PostgreSQL database. The aim is to make the demo accessible online without keeping a personal computer running.

The steps use AWS Management Console, AWS CLI and Systems Manager. Follow them from network and database setup through container deployment, frontend delivery, testing and cleanup.

#### Contents

1. [Workshop overview](5.1-Workshop-overview/)
2. [Prerequisites](5.2-Prerequisite/)
3. [Set up AWS infrastructure](5.3-Infrastructure/)
4. [Deploy the application](5.4-Deployment/)
5. [Testing, monitoring and cost](5.5-Testing-Monitoring-Cost/)
6. [Clean up resources](5.6-Cleanup/)
