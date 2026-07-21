---
title : "Overview"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

### AWS_OmniStay Project Overview

The **AWS_OmniStay** project is an online hotel booking web application, similar to a smaller version of Booking.com or Agoda.com. In addition to handling core business functions such as searching for available rooms by location and date, making real-time bookings, and managing transaction history, the main goal of this workshop is to deploy the entire system to the Amazon Web Services (AWS) cloud environment to optimize performance, security, and load-handling capability.

This workshop provides step-by-step guidance for building, configuring, and operating a complete **N-tier architecture** to demonstrate three fundamental characteristics of Cloud Computing:

### Project Links

- **Source code:** [AWS_OmniStay GitHub Repository](https://github.com/minhne198/AWS_OmniStay.git)
- **Demo video:** [AWS_OmniStay Demo Video Folder](https://drive.google.com/drive/folders/1UG2iVwxWX2OBc7nDoLslqoLCqRZxY5_L?usp=sharing)
- **Product link:** [AWS_OmniStay Production Website](https://d1gm8xt8e0mar4.cloudfront.net/public/home.html)

### Workshop Objectives

This workshop guides the step-by-step deployment of the **AWS_OmniStay** system on Amazon Web Services (AWS), from environment preparation to infrastructure setup, application deployment, and performance evaluation. After completing the workshop, the implementer will be able to:

- Prepare the development environment and configure the AWS account.
- Deploy the Frontend to **Amazon S3** and distribute content through **Amazon CloudFront**.
- Design and deploy network infrastructure using **Amazon VPC**, Public Subnets, and Private Subnets.
- Deploy the **ASP.NET Core (.NET 8)** application on **Amazon EC2** servers.
- Build an **Amazon RDS MySQL Multi-AZ** database system to ensure high availability.
- Deploy **Amazon ElastiCache Redis** to improve system response speed.
- Configure an **Application Load Balancer (ALB)** to distribute traffic to application servers.
- Set up an **Auto Scaling Group (ASG)** to automatically scale EC2 instances in or out based on CPU usage.
- Monitor resources with **Amazon CloudWatch** and control deployment costs using **AWS Budget**.
- Perform load testing with **Locust** and evaluate the effectiveness of Redis Cache and Auto Scaling through performance metrics.

### Workshop Scope

The workshop focuses on deploying and evaluating core AWS services used by the AWS_OmniStay online hotel booking system. The deployment scope includes:

| Component | Purpose |
| :--- | :--- |
| Amazon S3 | Stores the Frontend source code as a static website. |
| Amazon CloudFront | Distributes static content through a CDN network. |
| Origin Access Control (OAC) | Protects the S3 bucket and only allows CloudFront to access it. |
| Amazon VPC | Builds an isolated network environment for the system. |
| Amazon EC2 | Runs the ASP.NET Core Web API Backend. |
| Application Load Balancer | Balances traffic across multiple EC2 instances. |
| Auto Scaling Group | Automatically scales the number of EC2 instances based on system load. |
| Amazon RDS MySQL | Stores the system's business data. |
| Amazon ElastiCache Redis | Stores cached data to improve response speed. |
| Amazon CloudWatch | Monitors performance and configures alerts. |
| AWS Budget | Monitors and controls AWS service usage costs. |
| Locust | Simulates concurrent users to test system load-handling capacity. |

1. **High Availability (HA):** The system is distributed across multiple Availability Zones (AZs) to avoid a single point of failure. The website can continue operating even if one data center has a physical issue.
2. **Auto Scaling:** The compute infrastructure automatically adjusts the number of instances based on real user demand, scaling out under high load and scaling in under low load to optimize costs.
3. **Data Caching Mechanism:** Response speed is optimized through an in-memory cache layer, reducing direct queries to the relational database for repeated requests.

---

### Expected System Objectives

In addition to successfully deploying AWS services, the workshop also evaluates the effectiveness of the architecture through the following measurable goals:

- Ensure the system remains available when one Availability Zone has an issue by deploying redundant components.
- Automatically scale out EC2 instances when **CPU Utilization exceeds 70%** and scale in when the load decreases to optimize operating costs.
- Reduce response time for common queries from approximately **150 ms (Cache MISS)** to about **4-5 ms (Cache HIT)** by using Amazon ElastiCache Redis.
- Distribute static content through Amazon CloudFront to reduce access latency and improve page loading speed for users.
- Monitor and control AWS usage costs using AWS Budget with a **10 USD** alert threshold throughout the workshop deployment.

### Overall Architecture Diagram

The system is designed according to cloud architecture best practices from the AWS Well-Architected Framework, with a clear separation between the Public environment that receives traffic and the fully isolated Private environment for the application and data layers.

![AWS OmniStay Infrastructure Architecture](/images/aws-omnistay-architecture.png)

### Architecture Request Flow

The system request flow is described as follows:

```text
                User
                  |
                  v
          Amazon CloudFront
                  |
        (Static Content Request)
                  |
                  v
         Amazon S3 Private Bucket
                  |
                  |
        (API Request: /api/*)
                  v
     Application Load Balancer (ALB)
                  |
                  v
      Auto Scaling Group (EC2)
                  |
        ASP.NET Core Web API
          |                 |
          v                 v
 Amazon ElastiCache     Amazon RDS
       Redis             MySQL Multi-AZ
```

In this architecture, static files such as HTML, CSS, and JavaScript are stored in Amazon S3 and can only be accessed through Amazon CloudFront using Origin Access Control (OAC). For API requests, the Application Load Balancer distributes traffic to EC2 instances in the Auto Scaling Group. The backend checks Redis first to reduce response time. If the data is not available in the cache, the system queries Amazon RDS MySQL and then updates Redis for future requests.

#### Request Flow Explanation

* **Static content distribution layer (Frontend static assets):** Users access the website through **Amazon Route 53**, which resolves the domain name to the **Amazon CloudFront** CDN. The entire static HTML, CSS, and JavaScript interface is securely stored in an **Amazon S3 Private Bucket** and can only be accessed by CloudFront through **Origin Access Control (OAC)**. The outer layer is protected by **AWS WAF** to help prevent DDoS, SQL Injection, and XSS attacks.
* **Application logic layer (API Backend Layer):** All API requests from the browser using the `/api/*` path are routed by CloudFront to the **Application Load Balancer (ALB)** in the Public Subnets. The ALB continuously performs health checks and evenly distributes traffic to **Amazon EC2** virtual servers running the ASP.NET Core Web API through port `8080` inside the Private App Subnets.
* **Database and cache layer:** When a customer searches for available rooms, the .NET application checks **Amazon ElastiCache Redis** first. If the data already exists (Cache HIT), the result is returned immediately with very low latency (< 5 ms). If the data does not exist (Cache MISS), the system queries **Amazon RDS MySQL**, which is configured as Multi-AZ Primary + Standby for disaster recovery.

---

### Technology Stack Used

| Functional layer | Technology / Service used | Detailed role in the Workshop |
| :--- | :--- | :--- |
| **Client / Frontend** | HTML5, CSS3, Bootstrap 5.3, Vanilla JavaScript | Builds a responsive interface that asynchronously calls APIs using Fetch/Axios. |
| **API / Backend** | ASP.NET Core (.NET 8 LTS), Entity Framework Core | Handles business logic, JWT authentication, and transactions that prevent overbooking. |
| **Compute / Routing** | Amazon EC2, Application Load Balancer, Route 53 | Provides compute resources and load balancing for Web API traffic. |
| **Storage / CDN** | Amazon S3, Amazon CloudFront | Stores private frontend source code and accelerates page loading through Edge Locations. |
| **Database / Cache** | Amazon RDS MySQL 8.0, ElastiCache Redis | Stores long-term business data and provides a cache layer to accelerate searches. |
| **Operations / Security** | Amazon CloudWatch, CloudWatch Alarms, AWS Budget, IAM | Monitors resources, sets cost alerts, and manages secure permissions for EC2. |
| **Load Testing** | Locust (Python Framework) | Simulates hundreds of concurrent users to test Auto Scaling capability. |

### Expected Outcome

After completing the full workshop, the implementer will successfully build an online hotel booking system that can be deployed on Amazon Web Services with the following characteristics:

- The Frontend is hosted on Amazon S3 and distributed through Amazon CloudFront.
- The ASP.NET Core Backend runs stably behind the Application Load Balancer.
- The system can automatically scale using an Auto Scaling Group based on CPU usage.
- The Amazon RDS MySQL database is deployed in a Multi-AZ model to improve availability.
- Amazon ElastiCache Redis significantly reduces response time for common queries.
- The entire system is monitored with Amazon CloudWatch and cost-controlled with AWS Budget.
- Locust load testing results show that the system can respond well when many users access it concurrently, while also demonstrating the effectiveness of Redis Cache and Auto Scaling in improving performance and application scalability.
