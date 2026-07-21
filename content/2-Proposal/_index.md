---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# High-Availability Hotel Booking System on AWS

## High-load Online Hotel Booking System on AWS

### 1. Executive Summary

The high-load online hotel booking system on AWS is an e-commerce web application for travel and accommodation. The core goal of the project is to build a modern infrastructure solution that keeps the system stable and highly available, scales resources automatically according to real traffic, and optimizes response performance through caching.

By combining a high-performance **ASP.NET Core 8 (.NET 8 LTS)** backend with the strong cloud ecosystem of **Amazon Web Services (AWS)**, the project demonstrates how to solve high-traffic and failure-resilience problems faced by modern digital businesses.

### 2. Problem Statement

*Current problems* Traditional websites deployed on physical servers or a single-server model often face serious limitations in real environments:

* **Peak-season congestion**: During holidays or travel seasons, sudden traffic spikes overload server resources, causing service interruption, lag, or downtime. Renting high-capacity infrastructure from the beginning wastes cost during low-traffic periods.
* **Single Point of Failure**: The entire application depends on one server. If the server hardware fails or loses network connectivity, the website becomes unavailable, causing revenue loss and poor user experience.
* **Database overload**: When thousands of users repeatedly search for rooms, the relational database receives heavy direct query pressure, resulting in slow responses or database crashes.
* **Overbooking risk**: Without strong concurrency locking, two customers may successfully book and pay for the same room at the same time.

*Proposed solution* The application platform will move fully to a cloud-native model on AWS to solve these problems:

* **Load distribution and fault tolerance**: Use **Application Load Balancer (ALB)** with **Auto Scaling Group (ASG)** to distribute traffic evenly across **EC2** server instances in multiple Availability Zones. If one zone has a hardware failure, the system automatically reroutes traffic to the remaining zone smoothly within 30 seconds.
* **Demand-based auto scaling**: ASG monitors CPU Utilization, automatically increases server count during high load, and reduces instance count when traffic drops to optimize resource cost.
* **Speed optimization with Redis Cache**: Integrate **Amazon ElastiCache Redis** to cache common search results. Response time is reduced from about 150 ms to under 5 ms, while direct pressure on the RDS MySQL database is significantly reduced.
* **Strict overbooking prevention**: Apply **Row-Level Locking (SELECT FOR UPDATE)** with high-integrity EF Core database transactions using the Serializable isolation level to lock room data at payment time.

*Benefits and return on investment (ROI)*

* **Research and practical value**: The project acts as a complete blueprint for high availability in enterprise web application systems. The cloud infrastructure is defined as code using **AWS CDK (TypeScript)**, making it easier to manage, replicate, and reuse for future research.
* **Operational cost optimization**: By using flexible auto scaling policies, scaling in when user traffic is low, and taking advantage of **AWS Free Tier** for EC2, RDS, and Redis, the estimated cost of the experimental infrastructure is very low, under **10 USD (about 250,000 VND)** for the full project lifecycle.
* **Reduced administration time**: Monitoring is fully automated with CloudWatch, and incident alerts are sent immediately by email through Amazon SNS, reducing the need for a 24/7 system engineer.

### 3. Solution Architecture

The system uses a secure multi-tier architecture deployed inside an independent **Amazon VPC**, clearly separating public subnets from private subnets to ensure strong data security.

*AWS services used:*

* **Amazon VPC**: Provides an isolated network environment with 2 Public Subnets and 4 Private Subnets across 2 Availability Zones.
* **Application Load Balancer (ALB)**: Receives traffic on ports 80/443 and intelligently routes load to EC2 instances in Private Subnets.
* **Amazon EC2 & Auto Scaling Group**: Uses `t3.micro` instances running Amazon Linux 2023 as API servers, configured to scale automatically from 1 to a maximum of 4 servers.
* **Amazon RDS MySQL**: Stores core relational data such as hotels, rooms, and invoices, with Multi-AZ configuration for automated synchronization and failover.
* **Amazon ElastiCache (Redis)**: Provides a shared distributed cache for all EC2 instances in the ASG to accelerate queries.
* **Amazon S3 & CloudFront**: S3 stores frontend static assets and system images. CloudFront acts as a global CDN that distributes content quickly and securely through Origin Access Control (OAC).
* **Monitoring and Security**: Integrates AWS WAF for malicious request filtering, KMS for data encryption, Secrets Manager for secure environment variables, CloudWatch for metrics monitoring, and SNS for automated incident alerts.

### 4. Technical Implementation

*Implementation phases:*

1. **Phase 1: Network and security infrastructure setup (Week 1)**: Plan VPC, split subnets, configure route tables, NAT Gateways, and strict Security Groups.
2. **Phase 2: Cloud data layer initialization (Week 2)**: Create RDS MySQL and ElastiCache Redis on AWS, connect to the database, initialize schema, and seed sample data.
3. **Phase 3: Backend API development and logic optimization (Week 3)**: Build business controllers with ASP.NET Core 8, integrate Redis Cache logic and transaction handling to prevent overbooking.
4. **Phase 4: Frontend development (Week 4)**: Build a responsive web interface using HTML5, Bootstrap, and Vanilla JavaScript, then package and deploy it to Amazon S3 and CloudFront.
5. **Phase 5: ASG configuration and load testing (Weeks 5-6)**: Create Launch Template, build ALB, and configure Auto Scaling rules. Use **Locust** to simulate 300 concurrent users and test auto scaling and failover scenarios.
6. **Phase 6: Infrastructure as Code and automated monitoring (Weeks 7-8)**: Convert manual infrastructure configuration to **AWS CDK**, set up CloudWatch dashboards, and enable automated alerts through SNS.

*Technical requirements:*

* **Environment**: Visual Studio 2022 / VS Code, .NET 8 SDK, Node.js for AWS CDK, and AWS CLI.
* **Professional skills**: Understanding of Entity Framework Core, LINQ, asynchronous programming with Async/Await, thread-safe programming, advanced database transactions, cloud networking, routing, IAM Roles, and secure IAM Policies.

### 5. Roadmap and Milestones

The detailed schedule lasts **9 weeks**:

* **Week 1**: Start the project, set up VPC networking, and configure the local execution environment.
* **Week 2**: Deploy and configure RDS Database and Redis Cache successfully on AWS Cloud.
* **Week 3**: Complete 100% of Backend API features, including Auth, Search, Booking, and Admin, with Swagger integration.
* **Week 4**: Complete Frontend UI components and deploy successfully to S3/CloudFront.
* **Week 5**: Deploy the API to EC2 through Launch Template and configure ALB Target Group with successful Health Check recognition.
* **Week 6**: Perform Load Testing with Locust and tune Target CPU Tracking parameters.
* **Weeks 7-8**: Package complete AWS CDK source code, configure CloudWatch monitoring dashboards, and automate alerts.
* **Week 9**: Rehearse the application demo, prepare presentation slides, and present the project to the evaluation committee.

### 6. Budget Estimate

The system applies a strict cost optimization strategy, with most resource configurations staying within the **AWS Free Tier**.

*Estimated infrastructure cost when operating:*

* **Amazon EC2 (`t3.micro`)**: 0.00 USD, included in 750 monthly Free Tier hours.
* **Amazon RDS MySQL (`db.t3.micro`)**: 0.00 USD, included in 750 monthly Free Tier hours.
* **Amazon ElastiCache Redis (`cache.t3.micro`)**: 0.00 USD, covered by Free Tier benefits.
* **Application Load Balancer**: about 0.025 USD/hour, enabled only for load testing and demos, estimated about 1.50 USD.
* **NAT Gateway**: about 0.059 USD/hour, optimized with smart start/stop scripts, estimated about 3.00 USD.
* **Amazon S3 & CloudFront**: about 0.20 USD for static file storage and low-volume data transfer.

**Estimated total cost**: **< 10 USD (about 250,000 VND)** for the entire graduation project lifecycle by shutting down resources and reducing Desired Capacity to 0 when not used overnight.

### 7. Risk Assessment

*Risk matrix and mitigation strategy:*

* **Credential exposure risk**: Access Keys may be exposed when code is pushed to a public GitHub repository. *Mitigation:* Absolutely **DO NOT** hard-code passwords or secret keys in source code. Use a `.env` file declared in `.gitignore` and move fully to **IAM Role** attached directly to the EC2 Instance Profile.
* **Budget overrun risk (AWS bill shock)**: Paid resources may be left running after work sessions. *Mitigation:* Configure **AWS Budgets** with a **10 USD** alert threshold and send immediate email notifications when costs exceed the expected limit.
* **API database connection failure during demo**: Cloud resources may experience cold-start latency. *Mitigation:* Prepare an automated `warmup.sh` health-check script to start and warm up the full system, including RDS, EC2, and Redis, 30 minutes before the final presentation.

### 8. Expected Outcomes

* **Functional outcome**: A complete travel e-commerce application that supports registration/login, smart room search filters, real-time booking, and an admin dashboard.
* **Cloud technical outcome**:
  * Demonstrate **High Availability (HA)** visually by terminating a server under load in AWS Console while the system continues operating normally without response errors.
  * Demonstrate **Auto Scaling** with CloudWatch charts showing CPU reaching a high-load threshold and automatically increasing server count to handle traffic generated by Locust.
  * Optimize **Caching** by clearly measuring API response time dropping from about 150 ms to about 4 ms through distributed cache.
