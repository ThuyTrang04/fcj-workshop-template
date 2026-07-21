---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Deploy enterprise-grade file storage using **Amazon FSx for Windows**.
* Master the shared responsibility model and advanced identity administration with **IAM**, **Cognito**, and **AWS Organizations**.
* Set up single sign-on (**SSO**) and centralized security policy management with **SCP**.
* Apply international security standards through **AWS Security Hub** and encrypt data with **AWS KMS**.

### Tasks to complete this week:

| Day | Task | Start date | Completion date | Reference |
| --- | ---- | ---------- | --------------- | --------- |
| 2-3 | - Deploy **Amazon FSx (Lab 000025)**: set up a Multi-AZ file server, configure SMB, and enable data deduplication. <br> - Practice **IAM** administration: create User/Group, apply least-privilege policies, and use IAM Role. | 25/05/2026 | 26/05/2026 | Lab 000025 & AWS IAM |
| 4-5 | - Configure **Amazon Cognito**: set up User Pool and Identity Pool for mobile/web application authentication. <br> - Manage enterprise accounts with **AWS Organizations**: create OUs and configure **Service Control Policies (SCP)**. | 27/05/2026 | 28/05/2026 | AWS Security Documentation |
| 6 | - Deploy **AWS Identity Center (SSO)** for centralized access management. <br> - Practice data encryption with **AWS KMS**: manage master keys and data keys for data at rest. | 29/05/2026 | 29/05/2026 | AWS Study Group |
| 7-Sun | - Enable and configure **AWS Security Hub (Lab 000018)** to evaluate CIS compliance and AWS Best Practices. <br> - Collect lab screenshots, review configuration issues, and complete the week 7 report. | 30/05/2026 | 31/05/2026 | Lab 000018 & Personal |

### Results achieved in week 7:

* **Dedicated storage and identity administration:**
    * Successfully deployed **Amazon FSx**, optimized storage through Data Deduplication, and improved safety with Shadow Copies.
    * Understood how to move from using the Root account to a tightly controlled **IAM** permission model that follows strong security principles.
* **Large-scale administration and application authentication:**
    * Built an enterprise hierarchy with **AWS Organizations** and controlled the maximum permissions of member accounts using **SCP**.
    * Understood the independent user registration and authentication workflow through **Amazon Cognito**, reducing authentication load on the backend.
* **Centralized security and encryption:**
    * Used **AWS KMS** to protect sensitive data and learned how key management operates in a cloud environment.
    * Set up **Security Hub** as a command center for continuous monitoring, early vulnerability detection, and comparison against international security standards.
* **Create S3 Bucket:**
  ![alt text](image.png)
* **Create EC2 for Storage Gateway:**
  ![alt text](image-1.png)
* **Create Storage Gateway:**
  ![alt text](image-2.png)
  ![alt text](image-3.png)
  ![alt text](image-4.png)
  ![alt text](image-5.png)
* **Create File Shares**
  ![alt text](image-6.png)
* **Mount File shares on On-premises machine**
  ![alt text](image-7.png)
  ![alt text](image-8.png)
* **Create an SSD Multi-AZ file system**
  ![alt text](image-10.png)
* **Create an HDD Multi-AZ file system**
  ![alt text](image-11.png)
* **Create new file shares**
  ![alt text](image-12.png)
  ![alt text](image-13.png)
  ![alt text](image-14.png)
  ![alt text](image-15.png)
  ![alt text](image-16.png)
  ![alt text](image-17.png)
  ![alt text](image-18.png)
* **Test Performance**
  ![alt text](image-19.png)
  ![alt text](image-20.png)
* **DiskSpd Write tests**
  ![alt text](image-21.png)
* **fio read tests**
  ![alt text](image-22.png)
* **fio write tests**
  ![alt text](image-23.png)
* **Monitor Performance**
* **Enable data deduplication**
* **Enable shadow copies**
* **Manage user sessions and open files**
* **Enable user storage quotas**
* **Enable Continuous Access share**
* **Scale throughput capacity**
* **Scale storage capacity**
* **Create S3 bucket**
  ![alt text](image-24.png)
* **Load data**
  ![alt text](image-25.png)
* **Enable static website feature**
  ![alt text](image-26.png)
* **Configuring public objects**
  ![alt text](image-27.png)
  ![alt text](image-28.png)
  ![alt text](image-29.png)
* **Block all public access**
  ![alt text](image-30.png)
* **Enable Security Hub**
  ![alt text](image-31.png)
  ![alt text](image-32.png)
* **Security Score by Standards**
  ![alt text](image-33.png)
  ![alt text](image-34.png)
