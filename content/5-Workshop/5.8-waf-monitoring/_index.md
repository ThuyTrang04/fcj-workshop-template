---
title : "Configuring WAF, Monitoring, and Alerts"
date : 2024-01-01
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---

## Objective

This step adds protection and operations support for AWS_OmniStay. AWS WAF is attached to CloudFront to filter dangerous requests. CloudWatch, SNS, and CloudWatch Alarms are used to monitor the system, detect errors, and send alerts when resources show signs of overload.

## 1. Create an AWS WAF Web ACL for CloudFront

Go to **WAF & Shield** -> **Web ACLs** -> **Create web ACL**.

Configuration:

| Field | Value |
| --- | --- |
| Resource type | CloudFront distributions |
| Scope | Global |
| Name | `omnistay-cloudfront-waf` |
| Associated resource | CloudFront distribution of AWS_OmniStay |
| Default action | Allow |

Managed rule groups to add:

| Rule group | Purpose |
| --- | --- |
| `AWSManagedRulesCommonRuleSet` | Blocks common requests with abnormal patterns |
| `AWSManagedRulesKnownBadInputsRuleSet` | Blocks known malicious inputs |
| `AWSManagedRulesSQLiRuleSet` | Reduces SQL Injection risk |
| `AmazonIpReputationList` | Blocks IP addresses with poor reputation |

![VPC details](/images/581.jpg)
<p align="center"><em>Figure 5.8.1: Web ACL overview of `omnistay-cloudfront-waf`.</em></p>

## 2. Note About Rules for Image Uploads

In the AWS_OmniStay deployment documentation, there may be a case where image upload requests are blocked by CloudFront/WAF before reaching the backend. If the frontend includes multipart/form-data image upload functionality, check WAF sampled requests and add a narrowly scoped allow rule for the valid upload endpoint.

Principles when adding the rule:

- Only allow the required upload path, for example `/api/uploads/images`.
- Place the allow rule above managed rules that may block the request.
- Do not disable the entire WAF just to handle one endpoint.
- Verify that the backend still requires user authentication if the endpoint requires admin/owner permissions.

![VPC details](/images/582.jpg)
<p align="center"><em>Figure 5.8.2: Allow rule for image upload if the system implements upload functionality.</em></p>

## 3. Create an SNS Topic for Alerts

Go to **SNS** -> **Topics** -> **Create topic**.

Configuration:

| Field | Value |
| --- | --- |
| Type | Standard |
| Name | `omnistay-alerts` |
| Subscription protocol | Email |
| Endpoint | Email address that receives alerts |

After creating the subscription, open the email and confirm it so the status changes to `Confirmed`.

![VPC details](/images/583.jpg)
<p align="center"><em>Figure 5.8.3: SNS topic `omnistay-alerts`.</em></p>

## 4. Create a CloudWatch Dashboard

Go to **CloudWatch** -> **Dashboards** -> **Create dashboard**.

Configuration:

| Field | Value |
| --- | --- |
| Dashboard name | `OmniStay-Demo` |

Recommended widgets:

| Group | Metric |
| --- | --- |
| ALB | `RequestCount` |
| ALB | `HTTPCode_Target_5XX_Count` |
| ASG | `GroupDesiredCapacity` |
| ASG | `GroupInServiceInstances` |
| EC2 | `CPUUtilization` |
| RDS | `CPUUtilization` |
| RDS | `DatabaseConnections` |
| ElastiCache | `CPUUtilization` |
| ElastiCache | `CurrConnections` |

The dashboard helps quickly monitor the main components during demos or load testing.

![VPC details](/images/584.jpg)
<p align="center"><em>Figure 5.8.4: CloudWatch dashboard `OmniStay-Demo`.</em></p>

## 5. Create CloudWatch Alarms

Create a high CPU alarm for the Auto Scaling Group:

| Field | Value |
| --- | --- |
| Metric | ASG CPUUtilization |
| Resource | `omnistay-api-asg` |
| Condition | Greater than 70 |
| Notification | `omnistay-alerts` |
| Alarm name | `omnistay-asg-cpu-high` |

Create a 5XX error alarm from the ALB:

| Field | Value |
| --- | --- |
| Metric | `HTTPCode_Target_5XX_Count` |
| Resource | `omnistay-alb` |
| Condition | Greater than 10 |
| Notification | `omnistay-alerts` |
| Alarm name | `omnistay-alb-5xx-high` |

Create a high CPU alarm for RDS:

| Field | Value |
| --- | --- |
| Metric | RDS `CPUUtilization` |
| Resource | `omnistay-mysql` |
| Condition | Greater than 80 |
| Notification | `omnistay-alerts` |
| Alarm name | `omnistay-rds-cpu-high` |

![VPC details](/images/585.jpg)
<p align="center"><em>Figure 5.8.5: List of created CloudWatch Alarms.</em></p>

## 6. Control Costs During the Demo

Resources that require attention because they may generate hourly charges:

- NAT Gateway.
- Application Load Balancer.
- RDS MySQL.
- ElastiCache Redis/Valkey.
- AWS WAF.
- Public IPv4 address.
- CloudWatch logs/metrics if many logs are generated.

During the workshop, monitor the Billing dashboard and budget alerts. If no further demo is needed, reduce the ASG desired capacity or temporarily stop/delete costly resources according to a separate cleanup guide.

## Expected Result

After this step, CloudFront is protected by WAF, the system has an SNS topic for alerts, a CloudWatch dashboard for observing operations, and basic alarms for CPU, backend errors, and RDS.
