---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Strengthen data security and access management on AWS through **AWS KMS**, **IAM Policy**, **IAM Role**, and secure authentication mechanisms.
* Master data encryption, activity logging, and access monitoring with **AWS CloudTrail** and **Athena**.
* Learn database fundamentals and AWS storage solutions such as **Amazon RDS** and **Amazon Aurora**.
* Apply a modern permission model with **IAM Role**, reducing dependency on Access Keys and improving application security.
* Practice implementing **Least Privilege** and building a secure, manageable AWS environment.

### Tasks to complete this week:

| Day | Task | Start date | Completion date | Reference |
| --- | ---- | ---------- | --------------- | --------- |
| 2 | - Deploy **AWS KMS and data encryption (Lab 000033)**: create a KMS Key and configure data encryption on Amazon S3. <br> - Practice granting access to encryption keys through IAM Policy. | 08/06/2026 | 08/06/2026 | Lab 000033 |
| 3 | - Continue configuring **CloudTrail** to record access activity. <br> - Query logs with **Athena** and test resource access tracking. | 09/06/2026 | 09/06/2026 | Lab 000033 |
| 4 | - Learn database fundamentals: **Primary Key**, **Foreign Key**, **Index**, and the difference between **SQL** and **NoSQL**. <br> - Study **OLTP** and **OLAP** data processing models in enterprise systems. | 10/06/2026 | 10/06/2026 | AWS Database Overview |
| 5 | - Practice with **Amazon RDS** and **Amazon Aurora**: learn automatic administration, backups, and **Multi-AZ** deployment. <br> - Optimize performance and scalability for cloud data systems. | 11/06/2026 | 11/06/2026 | AWS RDS & Aurora |
| 6 | - Practice **advanced IAM (Lab 000044)**: create User, Group, IAM Role, and configure Switch Role. <br> - Deploy **IAM Role for EC2 (Lab 000048)** to access S3 without Access Keys. | 12/06/2026 | 12/06/2026 | Lab 000044 & Lab 000048 |
| 7 | - Practice AWS database overview content from **Lab 000005**: study storage architecture, backup mechanisms, scalability, and data optimization. <br> - Evaluate performance and high availability of database systems on cloud. | 13/06/2026 | 13/06/2026 | Lab 000005 |
| Sun | - Collect lab screenshots, review IAM, KMS, CloudTrail, and RDS configurations, and complete the week 9 report. <br> - Evaluate storage performance and data security in the AWS environment. | 14/06/2026 | 14/06/2026 | AWS Study Group & Personal |

### Results achieved in week 9:

* **Data security and encryption:**
    * Successfully deployed **AWS KMS** to encrypt data stored in Amazon S3, protecting data during storage and access.
    * Understood the process of creating, managing, and granting permissions for encryption keys in AWS.

* **System monitoring and activity tracking:**
    * Used **AWS CloudTrail** and **Athena** to record, analyze, and query system activity logs.
    * Improved the ability to monitor access and detect abnormal activity in the AWS environment.

* **Database knowledge and AWS storage:**
    * Understood fundamentals such as **Primary Key**, **Foreign Key**, **Index**, and the difference between **SQL** and **NoSQL** models.
    * Studied and practiced with **Amazon RDS** and **Amazon Aurora**, including **Automated Backup**, **Multi-AZ**, and global scalability.
    * Understood the difference between transactional processing (**OLTP**) and analytical data warehousing (**OLAP**) to choose suitable architectures for each system need.
    * Understood the role of optimized data design in improving performance, stability, and scalability for real applications.

* **Access management and advanced security:**
    * Successfully configured **IAM User**, **IAM Role**, **Switch Role**, and advanced access control mechanisms.
    * Applied the **Least Privilege** principle effectively, reducing credential exposure risk and improving enterprise security.

* **Modern permission model deployment:**
    * Applied **IAM Role for EC2** to access AWS resources without storing Access Keys in the application.
    * Understood temporary credentials and practical security administration methods.
* **Create Policy and Role**
  ![alt text](image.png)
  ![alt text](image-1.png)
* **Create Group and User**
  ![alt text](image-2.png)
  ![alt text](image-4.png)
  ![alt text](image-5.png)
* **Create Key Management Service**
  ![alt text](image-6.png)
  ![alt text](image-7.png)
* **Create Amazon S3**
  ![alt text](image-8.png)
  ![alt text](image-9.png)
* **Create AWS CloudTrail and Amazon Athena**
  ![alt text](image-10.png)
  ![alt text](image-11.png)
  ![alt text](image-12.png)
  ![alt text](image-13.png)
  ![alt text](image-14.png)
* **Create IAM Group**
  ![alt text](image-15.png)
* **Create IAM User**
  ![alt text](image-16.png)
  ![alt text](image-17.png)
* **Configure Role Condition**
  ![alt text](image-18.png)
  ![alt text](image-19.png)
  ![alt text](image-20.png)
* **IAM role on EC2**
  ![alt text](image-21.png)
* **Prerequisite Steps**
  ![alt text](image-22.png)
* **Create EC2 instance**
  ![alt text](image-23.png)
* **Create RDS database instance**
  ![alt text](image-24.png)
  ![alt text](image-25.png)
* **Application Deployment**
  ![alt text](image-26.png)
  ![alt text](image-27.png)
