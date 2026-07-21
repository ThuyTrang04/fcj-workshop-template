---
title : "Configuring Network Security and Access Permissions"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

## Objective

After creating the VPC and subnets, the next step is to configure the security layer for each tier of the system. AWS_OmniStay uses Security Groups to restrict traffic according to the correct flow:

```text
Internet -> CloudFront -> ALB -> EC2 backend -> RDS MySQL / Redis
```

The backend is not exposed directly to the Internet. RDS and Redis also do not allow access from `0.0.0.0/0`; only the backend EC2 instances can connect to the data tiers.

## 1. Create a Security Group for the ALB

Go to **EC2** -> **Security Groups** -> **Create security group**.

Configuration:

| Field | Value |
| --- | --- |
| Security group name | `SG-ALB` |
| Description | `Allow public HTTP to ALB` |
| VPC | `omnistay-vpc` |

Inbound rule:

| Type | Port | Source | Purpose |
| --- | --- | --- | --- |
| HTTP | 80 | `0.0.0.0/0` | Allows users to access the ALB through HTTP |

Keep the default **All traffic** outbound rule.

![VPC details](/images/541.jpg)
<p align="center"><em>Figure 5.4.1: Inbound rules of `SG-ALB`.</em></p>

## 2. Create a Security Group for the EC2 Backend

Configuration:

| Field | Value |
| --- | --- |
| Security group name | `SG-EC2` |
| Description | `Allow ALB to API instances` |
| VPC | `omnistay-vpc` |

Inbound rule:

| Type | Port | Source | Purpose |
| --- | --- | --- | --- |
| Custom TCP | 8080 | `SG-ALB` | Only the ALB can call the backend API |

With this configuration, the EC2 backend does not receive traffic directly from the Internet. Requests must go through the ALB before reaching the ASP.NET Core application.

![VPC details](/images/542.jpg)
<p align="center"><em>Figure 5.4.2: Inbound rules of `SG-EC2`.</em></p>

## 3. Create a Security Group for RDS MySQL

Configuration:

| Field | Value |
| --- | --- |
| Security group name | `SG-RDS` |
| Description | `Allow EC2 to MySQL` |
| VPC | `omnistay-vpc` |

Inbound rule:

| Type | Port | Source | Purpose |
| --- | --- | --- | --- |
| MySQL/Aurora | 3306 | `SG-EC2` | Only backend EC2 instances can connect to MySQL |

![VPC details](/images/543.jpg)
<p align="center"><em>Figure 5.4.3: Inbound rules of `SG-RDS`.</em></p>

## 4. Create a Security Group for Redis/Valkey

Configuration:

| Field | Value |
| --- | --- |
| Security group name | `SG-Redis` |
| Description | `Allow EC2 to Redis cache` |
| VPC | `omnistay-vpc` |

Inbound rule:

| Type | Port | Source | Purpose |
| --- | --- | --- | --- |
| Custom TCP | 6379 | `SG-EC2` | Only backend EC2 instances can connect to Redis |

![VPC details](/images/544.jpg)
<p align="center"><em>Figure 5.4.4: Inbound rules of `SG-Redis`.</em></p>

## 5. Create an IAM Role for the EC2 Backend

The EC2 backend needs permissions to read artifacts from S3, use Session Manager for server inspection, and send logs/metrics to CloudWatch. Do not use hard-coded access keys on EC2.

Go to **IAM** -> **Roles** -> **Create role**.

Configuration:

| Field | Value |
| --- | --- |
| Trusted entity | AWS service |
| Use case | EC2 |
| Role name | `EC2-HotelAPI-Role` |

Policies to attach:

| Policy | Purpose |
| --- | --- |
| `AmazonSSMManagedInstanceCore` | Connect to EC2 through Session Manager |
| `CloudWatchAgentServerPolicy` | Send logs/metrics to CloudWatch |
| `AmazonS3ReadOnlyAccess` | Allow EC2 to download backend artifacts from the S3 artifact bucket |

In a real production environment, S3 permissions should be limited to the exact artifact bucket instead of using read-only access to all S3. Within the demo scope, this configuration makes deployment faster and easier to verify.

![VPC details](/images/545.png)
<p align="center"><em>Figure 5.4.5: EC2-HotelAPI-Role.</em></p>

## 6. Verify the Layered Security Principle

After creation, verify the allowed port flow:

| Layer | Open port | Valid source |
| --- | --- | --- |
| ALB | 80 | Internet |
| EC2 backend | 8080 | `SG-ALB` |
| RDS MySQL | 3306 | `SG-EC2` |
| Redis/Valkey | 6379 | `SG-EC2` |

Do not open public SSH/RDP unless necessary. When EC2 inspection is needed, prioritize **AWS Systems Manager Session Manager** through the IAM Role.

## Expected Result

After this step, the system tiers are isolated according to their roles. The ALB is the public entry point, the EC2 backend is placed in private subnets, and RDS and Redis only accept connections from the backend. EC2 has an IAM Role to retrieve artifacts and support operational checks without storing access keys in the source code.
