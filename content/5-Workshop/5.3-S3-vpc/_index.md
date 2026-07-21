---
title : "Building Network Infrastructure on AWS"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

## Objective

This step creates the foundational network layer for AWS_OmniStay. The system needs public subnets to receive traffic from the Internet through the ALB and NAT Gateway, and private subnets to run backend EC2 instances, RDS MySQL, and ElastiCache Redis more securely.

The network model uses two Availability Zones to improve availability:

- Two public subnets for the ALB and NAT Gateway.
- Two private app subnets for the EC2 backend.
- Two private data subnets for RDS and Redis.

## 1. Create a VPC

Go to **VPC** -> **Your VPCs** -> **Create VPC**.

Configuration:

| Field | Value |
| --- | --- |
| Resource to create | VPC only |
| Name tag | `omnistay-vpc` |
| IPv4 CIDR | `10.0.0.0/16` |
| Tenancy | Default |

After creation, verify that the VPC has CIDR `10.0.0.0/16` and is in the correct Region, `ap-southeast-1`.

![VPC details](/images/531.jpg)
<p align="center"><em>Figure 5.3.1: VPC created successfully.</em></p>

## 2. Create Six Subnets

Go to **VPC** -> **Subnets** -> **Create subnet**. All subnets belong to `omnistay-vpc`.

| Subnet name | AZ | IPv4 CIDR | Role |
| --- | --- | --- | --- |
| `omnistay-public-a` | `ap-southeast-1a` | `10.0.1.0/24` | Public subnet for ALB/NAT |
| `omnistay-public-b` | `ap-southeast-1b` | `10.0.2.0/24` | Public subnet for ALB/NAT |
| `omnistay-app-a` | `ap-southeast-1a` | `10.0.10.0/24` | Private app subnet for EC2 |
| `omnistay-app-b` | `ap-southeast-1b` | `10.0.11.0/24` | Private app subnet for EC2 |
| `omnistay-data-a` | `ap-southeast-1a` | `10.0.20.0/24` | Private data subnet for RDS/Redis |
| `omnistay-data-b` | `ap-southeast-1b` | `10.0.21.0/24` | Private data subnet for RDS/Redis |

After creating the two public subnets, enable **Auto-assign public IPv4 address** for `omnistay-public-a` and `omnistay-public-b`.

![VPC details](/images/532.jpg)
<p align="center"><em>Figure 5.3.2: Six subnets created.</em></p>

## 3. Create an Internet Gateway

Go to **VPC** -> **Internet Gateways** -> **Create internet gateway**.

Configuration:

| Field | Value |
| --- | --- |
| Name tag | `omnistay-igw` |
| Attach VPC | `omnistay-vpc` |

After creation, select the newly created Internet Gateway, go to **Actions** -> **Attach to VPC**, and attach it to `omnistay-vpc`.

![VPC details](/images/533.jpg)
<p align="center"><em>Figure 5.3.3: Internet Gateway.</em></p>

![VPC details](/images/534.jpg)
<p align="center"><em>Figure 5.3.4: Attach to VPC.</em></p>

## 4. Create a Public Route Table

Go to **VPC** -> **Route tables** -> **Create route table**.

Configuration:

| Field | Value |
| --- | --- |
| Name | `omnistay-public-rt` |
| VPC | `omnistay-vpc` |

Routes:

| Destination | Target |
| --- | --- |
| `10.0.0.0/16` | local |
| `0.0.0.0/0` | `omnistay-igw` |

Subnet associations:

- `omnistay-public-a`
- `omnistay-public-b`

![VPC details](/images/535.jpg)
<p align="center"><em>Figure 5.3.5: Public route table with route configured.</em></p>

## 5. Create NAT Gateways

NAT Gateway allows EC2 instances in private app subnets to access the Internet outbound to download packages, call AWS services, or send logs without requiring public IP addresses.

Create the first NAT Gateway:

| Field | Value |
| --- | --- |
| Name | `omnistay-nat-a` |
| Subnet | `omnistay-public-a` |
| Connectivity type | Public |
| Elastic IP allocation | Automatic |

Create the second NAT Gateway:

| Field | Value |
| --- | --- |
| Name | `omnistay-nat-b` |
| Subnet | `omnistay-public-b` |
| Connectivity type | Public |
| Elastic IP allocation | Automatic |

![VPC details](/images/537.jpg)
<p align="center"><em>Figure 5.3.7: Creating a NAT Gateway.</em></p>

## 6. Create Private Route Tables for App Subnets

Create a route table for the app subnet in AZ-a:

| Field | Value |
| --- | --- |
| Name | `omnistay-app-a-rt` |
| VPC | `omnistay-vpc` |
| Route | `0.0.0.0/0 -> omnistay-nat-a` |
| Subnet association | `omnistay-app-a` |

Create a route table for the app subnet in AZ-b:

| Field | Value |
| --- | --- |
| Name | `omnistay-app-b-rt` |
| VPC | `omnistay-vpc` |
| Route | `0.0.0.0/0 -> omnistay-nat-b` |
| Subnet association | `omnistay-app-b` |

Private data subnets that contain RDS and Redis do not need an Internet route in the basic demo flow. They only receive internal connections from backend EC2 instances through Security Groups.

![VPC details](/images/536.jpg)
<p align="center"><em>Figure 5.3.6: Creating a Private App Route Table.</em></p>

## Expected Result

After this step, the system has its own VPC, separated public/private subnets, Internet access for public subnets, NAT Gateways for app subnets, and a network foundation ready for deploying ALB, EC2, RDS, and Redis.
