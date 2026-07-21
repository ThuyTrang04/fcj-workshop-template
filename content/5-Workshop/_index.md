---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Deploying the AWS OmniStay System on AWS

The Workshop section records the step-by-step deployment process of the **AWS_OmniStay** hotel booking website on Amazon Web Services. The content focuses on building the infrastructure, deploying the backend, deploying the frontend, configuring security, testing the system, and collecting screenshots as evidence.

The system is deployed using a multi-tier architecture:

- The static frontend is stored in a private Amazon S3 bucket and distributed through Amazon CloudFront.
- The ASP.NET Core Web API backend runs on Amazon EC2 instances in a private subnet.
- The Application Load Balancer receives requests from CloudFront and forwards them to the backend.
- The Auto Scaling Group manages the number of backend EC2 instances.
- Amazon RDS for MySQL stores business data.
- Amazon ElastiCache Redis/Valkey is used as a cache layer for the hotel search flow.
- AWS WAF, IAM, Security Groups, Secrets Manager, Parameter Store, and CloudWatch support security, configuration, and operations.

## Contents

1. [Overview](5.1-Workshop-overview/)
2. [Preparation Before Deployment](5.2-Prerequiste/)
3. [Building the Network Infrastructure on AWS](5.3-S3-vpc/)
4. [Configuring Network Security and Access Permissions](5.4-S3-onprem/)
5. [Creating the Data Layer and System Configuration](5.5-Policy/)
6. [Deploying the Backend API to AWS](5.6-Cleanup/)
7. [Deploying the Frontend to S3 and CloudFront](5.7-frontend-cloudfront/)
8. [Configuring WAF, Monitoring, and Alerts](5.8-waf-monitoring/)
9. [Testing the System After Deployment](5.9-system-testing/)

## Screenshot Note Convention

In each deployment step, locations that need screenshots are marked with a note line.

When completing the report, replace these notes with real screenshots from the AWS Console, browser, or terminal.
