---
title: "Blog 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.6. </b> "
---

{{% notice warning %}}
**Note:** The information below is for reference only. Please do not copy it verbatim into your own report, including this warning.
{{% /notice %}}

# Getting Started with Healthcare Data Lakes: Using Microservices

Data lakes can help hospitals and healthcare organizations turn data into business insights and maintain business continuity while protecting patient privacy. A **data lake** is a centralized, managed, and secure repository used to store all data, both in its raw form and in processed form for analysis. A data lake allows you to break down data silos and combine different types of analytics to gain insights and make better business decisions.

This blog post is part of a larger series about getting started with healthcare data lakes. In my previous post in the series, *"Getting started with healthcare data lakes: Diving deep into Amazon Cognito"*, I focused on the specific details of using Amazon Cognito and Attribute-Based Access Control (ABAC) to authenticate and authorize users in a healthcare data lake solution. In this blog, I describe how the solution has evolved at the basic level, including the design decisions I made and the additional features used. You can refer to the solution's code samples in the Git repository.

---

## Architecture Guidance

The main change since the previous presentation of the overall architecture is the separation of a single service into a set of smaller services to improve maintainability and flexibility. Integrating a large amount of different healthcare data often requires specialized connectors for each format. By keeping them packaged separately as microservices, we can add, remove, or modify each connector without affecting the others. The microservices are loosely connected through centralized publish/subscribe messaging in what I call a "pub/sub hub".

This solution represents another reasonable sprint iteration from my previous post. The scope is still limited to simple ingestion and parsing of **HL7v2 messages** formatted according to **Encoding Rule 7 (ER7)** through a REST interface.

**The solution architecture is now as follows:**

> *Figure 1. Overall architecture; the colored boxes represent separate services.*

---

Although the term *microservices* has some inherent ambiguity, several characteristics are common:

- They are small, autonomous, and loosely coupled.
- They are reusable and communicate through well-defined interfaces.
- They are specialized to solve one specific task.
- They are often deployed in an **event-driven architecture**.

When defining boundaries between microservices, the following factors should be considered:

- **Internal:** technologies used, performance, reliability, and scalability.
- **External:** dependent functionality, frequency of change, and reusability.
- **People:** team ownership and management of *cognitive load*.

---

## Technology Choices and Communication Scope

| Communication scope | Technologies / patterns to consider |
| --- | --- |
| Within one microservice | Amazon Simple Queue Service (Amazon SQS), AWS Step Functions |
| Between microservices within one service | AWS CloudFormation cross-stack references, Amazon Simple Notification Service (Amazon SNS) |
| Between services | Amazon EventBridge, AWS Cloud Map, Amazon API Gateway |

---

## The Pub/Sub Hub

Using a **hub-and-spoke** architecture, or message broker, works well with a small number of closely related microservices.

- Each microservice depends only on the *hub*.
- Connections between microservices are limited to the content of the published message.
- The number of synchronous calls is reduced because pub/sub is one-way asynchronous push messaging.

The disadvantage is that **coordination and monitoring** are required to prevent a microservice from processing the wrong message.

---

## Core Microservice

This microservice provides the foundational data and communication layer, including:

- An **Amazon S3** bucket for data.
- **Amazon DynamoDB** for the data catalog.
- **AWS Lambda** to write messages to the data lake and catalog.
- An **Amazon SNS** topic used as the *hub*.
- An **Amazon S3** bucket for artifacts such as Lambda code.

> Only indirect write access to the data lake through the Lambda function is allowed, which helps ensure consistency.

---

## Front Door Microservice

- Provides API Gateway for external REST interactions.
- Performs authentication and authorization based on **OIDC** through **Amazon Cognito**.
- Uses a self-managed *deduplication* mechanism with DynamoDB instead of SNS FIFO because:
  1. SNS deduplication TTL is only five minutes.
  2. SNS FIFO requires SQS FIFO.
  3. The sender can be proactively informed when a message is a duplicate.

---

## Staging ER7 Microservice

- A Lambda "trigger" subscribes to the pub/sub hub and filters messages by attribute.
- Step Functions Express Workflow converts ER7 to JSON.
- Two Lambda functions are used:
  1. One function corrects the ER7 format, including newline and carriage return characters.
  2. One function handles parsing logic.
- Successful results or errors are published back to the pub/sub hub.

---

## New Features in the Solution

### 1. AWS CloudFormation Cross-stack References

Example *outputs* in the core microservice:

```yaml
Outputs:
  Bucket:
    Value: !Ref Bucket
    Export:
      Name: !Sub ${AWS::StackName}-Bucket
  ArtifactBucket:
    Value: !Ref ArtifactBucket
    Export:
      Name: !Sub ${AWS::StackName}-ArtifactBucket
  Topic:
    Value: !Ref Topic
    Export:
      Name: !Sub ${AWS::StackName}-Topic
  Catalog:
    Value: !Ref Catalog
    Export:
      Name: !Sub ${AWS::StackName}-Catalog
  CatalogArn:
    Value: !GetAtt Catalog.Arn
    Export:
      Name: !Sub ${AWS::StackName}-CatalogArn
```
