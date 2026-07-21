---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Optimize cost and automate AWS resource management using **AWS Lambda**, **CloudWatch**, and resource lifecycle management.
* Master resource management with **Resource Tags**, **Resource Groups**, and advanced access control.
* Apply permission controls using **IAM Policy**, **Resource Tags**, and **IAM Permission Boundary**.
* Improve administration, security control, and implementation of the **Least Privilege** principle in AWS.

### Tasks to complete this week:

| Day | Task | Start date | Completion date | Reference |
| --- | ---- | ---------- | --------------- | --------- |
| 2 | - Deploy **EC2 cost optimization (Lab 000022)**: use **AWS Lambda** with **CloudWatch Events** to automatically start/stop EC2 instances on a schedule. <br> - Create an IAM Role for Lambda and verify the automation. | 01/06/2026 | 01/06/2026 | Lab 000022 |
| 3 | - Continue testing and verifying the EC2 automation mechanism. <br> - Handle errors, monitor logs through CloudWatch, and optimize the operations process. | 02/06/2026 | 02/06/2026 | Lab 000022 |
| 4 | - Practice **Resource Tags and Resource Groups (Lab 000027)**: tag EC2, S3, VPC, and group resources by management criteria. | 03/06/2026 | 03/06/2026 | Lab 000027 |
| 5 | - Practice **IAM Policy with Resource Tags (Lab 000028)**: configure tag-based access control conditions. <br> - Test permissions following the least-privilege principle. | 04/06/2026 | 04/06/2026 | Lab 000028 |
| 6 | - Deploy **IAM Permission Boundary (Lab 000030)**: create a policy that limits EC2 permissions by Region. <br> - Apply the Permission Boundary to an IAM User and test access. | 05/06/2026 | 05/06/2026 | Lab 000030 |
| 7 | - Verify **Permission Boundary** behavior and test permission limits across Regions. <br> - Evaluate access control effectiveness and AWS resource security. | 06/06/2026 | 06/06/2026 | Lab 000030 |
| Sun | - Collect lab screenshots, review configuration errors, check resources, and complete the week 8 report. | 07/06/2026 | 07/06/2026 | AWS Study Group & Personal |

### Results achieved in week 8:

* **Cost optimization and automation:**
    * Successfully deployed automated start/stop for **Amazon EC2** using **AWS Lambda**, reducing manual administration and optimizing resource cost.
    * Understood how **Lambda**, **CloudWatch**, and **IAM Role** work together in AWS resource automation.

* **Resource management and system classification:**
    * Used **Resource Tags** and **Resource Groups** confidently to organize resources by environment and purpose.
    * Built a centralized resource management workflow that supports efficient operations in larger systems.

* **Access control and advanced security:**
    * Successfully configured **IAM Policy** with tag conditions and deployed **IAM Permission Boundary** to limit maximum user permissions.
    * Understood how to apply **Least Privilege**, strengthen access control, and reduce security risks in an enterprise environment.
* **Create VPC**
  ![alt text](image.png)
* **Create Security Group**
  ![alt text](image-1.png)
* **Create EC2 instance**
  ![alt text](image-2.png)
* **Create Tag for Instance**
  ![alt text](image-3.png)
* **Create Role for Lambda**
  ![alt text](image-4.png)
* **Function stop instance**
  ![alt text](image-5.png)
  ![alt text](image-6.png)
  ![alt text](image-7.png)
  ![alt text](image-8.png)
* **Function start instance**
  ![alt text](image-9.png)
* **Check Results**
  ![alt text](image-10.png)
  ![alt text](image-11.png)
* **Create EC2 Instance with tag**
  ![alt text](image-12.png)
  ![alt text](image-13.png)
* **Managing Tags in AWS Resources**
  ![alt text](image-14.png)
  ![alt text](image-15.png)
* **Filter resources by tag**
* **Using tags with CLI**
  ![alt text](image-15.png)
  ![alt text](image-16.png)
  ![alt text](image-17.png)
* **Create a Resource Group**
  ![alt text](image-18.png)
* **Create IAM user**
  ![alt text](image-19.png)
* **Create IAM Policy**
  ![alt text](image-20.png)
* **Create IAM Role**
  ![alt text](image-21.png)
* **Check Policy**
* **Switch Roles**
  ![alt text](image-22.png)
* **Check IAM Policy**
* **Initiating access to EC2 console in AWS Region - Tokyo**
  ![alt text](image-24.png)
* **Initiating access to EC2 console in AWS Region - North Virginia**
  ![alt text](image-23.png)
* **Proceed to create EC2 instance when Tags are missing or invalid**
  ![alt text](image-25.png)
* **Edit Resource Tag on EC2 Instance**
  ![alt text](image-26.png)
* **Create Restriction Policy**
  ![alt text](image-27.png)
* **Create IAM Limited User**
  ![alt text](image-28.png)
* **Test IAM User Limits**
  ![alt text](image-29.png)
