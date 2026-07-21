---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Build durable object storage infrastructure with **Amazon S3** and deploy a static website.
* Master advanced isolated networking with **VPC**, **Public/Private Subnets**, and **NAT Gateway**.
* Configure data security and secure connectivity using **Versioning**, **Replication**, and **VPC Endpoints**.
* Learn **Disaster Recovery** strategies and centralized backup management with **AWS Backup**.

### Tasks to complete this week:

| Day | Task | Start date | Completion date | Reference |
| --- | ---- | ---------- | --------------- | --------- |
| 2-3 | - Create an **S3 Bucket**, configure **Static Website Hosting**, and integrate **CloudFront**. <br> - Set up a **Bucket Policy** to manage public access securely. | 18/05/2026 | 19/05/2026 | S3 Lab (000057) |
| 4-5 | - Configure an **advanced VPC**: split subnets, set up Internet Gateway and NAT Gateway. <br> - Deploy **VPC Endpoints** to connect privately to S3 without going through the internet. | 20/05/2026 | 21/05/2026 | VPC Lab (000013-14) |
| 6 | - Practice **Versioning** and **Multi-Region Replication** to improve availability. <br> - Control network traffic through **NACLs** and **Security Groups**. | 22/05/2026 | 22/05/2026 | AWS Study Group |
| 7-Sun | - Set up a centralized backup plan with **AWS Backup**. <br> - Collect lab screenshots and complete the week 6 report. | 23/05/2026 | 24/05/2026 | Personal |

### Results achieved in week 6:

* **Storage and content distribution:**
    * Successfully deployed a static website optimized for global access by combining **S3** and **CloudFront**.
    * Learned object lifecycle management and **Storage Classes** to optimize cost.
* **Advanced network administration:**
    * Built a secure isolated network where servers in Private Subnets access the internet through **NAT Gateway** while maintaining security.
    * Deployed **VPC Peering** and **VPC Endpoints** to optimize internal data paths on AWS.
* **Security and high availability:**
    * Understood **RTO/RPO** metrics and disaster recovery strategies through multi-region data replication.
    * Used **AWS Backup** to manage backups across multiple services from a single interface.
* **Create S3 bucket**
  ![alt text](image.png)
* **Upload Data**
  ![alt text](image-1.png)
  ![alt text](image-2.png)
* **Enable static website feature**
  ![alt text](image-3.png)
### Results achieved:
  * The bucket now has a website endpoint URL.
  * S3 will use index.html as the default page.
  * The bucket is configured to host static content.
  * It is ready for website files to be uploaded.
* **Configuring public access block**
   ![alt text](image-4.png)
   ![alt text](image-5.png)
   ![alt text](image-6.png)
### Results achieved:
  * ACLs were enabled on the S3 bucket.
  * Appropriate object ownership settings were configured.
  * Public access to website objects was allowed.
  * The bucket was prepared for static website hosting.
* **Test website**
  ![alt text](image-7.png)
* **Block all public access**
  ![alt text](image-8.png)
  ![alt text](image-9.png)
* **Configure Amazon CloudFront**
* **Bucket Versioning**
  ![alt text](image-10.png)
  ![alt text](image-11.png)
  ![alt text](image-12.png)
* **Create S3 bucket**
  ![alt text](image-13.png)
  ![alt text](image-14.png)
  ![alt text](image-15.png)
  ![alt text](image-16.png)
* **VMWare Workstation**
  ![alt text](image-17.png)
  ![alt text](image-18.png)
  ![alt text](image-19.png)
  ![alt text](image-20.png)
  ![alt text](image-21.png)
  ![alt text](image-22.png)
  ![alt text](image-23.png)
* **Import virtual machine to AWS**
  ![alt text](image-24.png)
* **Deploy Instance from AMI**
  ![alt text](image-25.png)
  ![alt text](image-26.png)
* **Setting up S3 bucket ACL**
  ![alt text](image-27.png)
  ![alt text](image-28.png)
  ![alt text](image-29.png)
* **Export virtual machine from Instance**
  ![alt text](image-30.png)
  ![alt text](image-31.png)
* **Export virtual machine from AMI**
  ![alt text](image-32.png)
  ![alt text](image-33.png)

{{% notice info %}}
**Summary:** Week 6 strengthened the Cloud Engineer mindset by combining the unlimited storage capability of S3 with the flexibility and security of VPC. This is a core foundation for building large-scale, highly reliable applications on AWS.
{{% /notice %}}
