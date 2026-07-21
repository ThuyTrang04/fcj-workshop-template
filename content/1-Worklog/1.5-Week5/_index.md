---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Deploy a hub-and-spoke network architecture using **AWS Transit Gateway (TGW)** to connect multiple VPCs.
* Practice **Infrastructure as Code (IaC)** with CloudFormation to create complex infrastructure.
* Study **Amazon EC2** architecture in depth, including Intel, AMD, Graviton chips and the Nitro virtualization system.
* Manage storage effectively by comparing **EBS** for durability and **Instance Store** for high speed.
* Automate server configuration with **User Data** and retrieve instance information through **Metadata**.
* Set up **S3 VPC Endpoints** and **Hybrid DNS** to secure data access and synchronize name resolution.
* Study **AWS MGN** migration service and **Disaster Recovery** strategies.

### Tasks to complete this week:

| Day | Task | Start date | Completion date | Reference |
| --- | ---- | ---------- | --------------- | --------- |
| 2-3 | - Use CloudFormation to create 4 VPCs and sample server systems. <br> - Set up **Transit Gateway**, attachments, and TGW route table planning. | 11/05/2026 | 12/05/2026 | AWS Module 02 |
| 4 | - Configure VPC routing and test connectivity between Private Subnets. <br> - Use **Reachability Analyzer** to analyze packet flow. | 13/05/2026 | 13/05/2026 | AWS Module 02 |
| 5 | - Study EC2 Instance Types, Graviton chips, and the benefits of Nitro virtualization. <br> - Compare snapshot backup mechanisms: full vs incremental. | 14/05/2026 | 14/05/2026 | AWS Module 03 |
| 6 | - Practice configuring **User Data** to automatically install a Web Server. <br> - Test querying **Metadata** through the internal IP address `169.254.169.254`. <br> - Learn **Auto Scaling** to automatically scale virtual machines. <br> - Configure **S3 Gateway Endpoint** and **Interface Endpoint (PrivateLink)** for private S3 access. <br> - Set up a simulated VPN and DNS to support private on-premises access to S3. | 15/05/2026 | 15/05/2026 | AWS Module 03 |
| 7-Sun | - Compare performance and data durability between **EBS** and **Instance Store**. <br> - Deploy a lightweight server with **Amazon Lightsail** and configure file sharing with **EFS/FSx**. <br> - Study **AWS MGN** migration service and Disaster Recovery strategies. <br> - **Clean up:** Delete TGW Attachments, TGW, and CloudFormation Stack to avoid charges. | 16/05/2026 | 17/05/2026 | Personal |

### Results achieved in week 5:

* **Networking architecture:**
    * Replaced complex VPC Peering patterns with **Transit Gateway**, making centralized management and expansion easier.
    * Learned how to use a Bastion Host to SSH into servers inside private networks securely.
* **Compute and storage resources:**
    * Understood how to optimize cost by choosing the right instance type and taking advantage of ARM Graviton chips.
    * Understood the data loss risks of **Instance Store** and the durability of **EBS**, which replicates data across 3 nodes in one AZ.
    * Automated software deployment during server initialization using User Data.
* **Connectivity optimization:** Replaced complex peering with Transit Gateway and secured S3 data access through VPC Endpoints.
* **Generate Key Pair**
  ![alt text](image.png)
* **Create and initialize CloudFormation Template**
 ![alt text](image-1.png)
* **Create Transit Gateway**
 ![alt text](image-2.png)
* **Create Transit Gateway Attachments**
  ![alt text](image-4.png)
  ![alt text](image-5.png)
  ![alt text](image-6.png)
* **Create Transit Gateway Route Tables**
* **Create Associations**
  ![alt text](image-7.png)
* **Configure Route Table Propagations**
  ![alt text](image-8.png)
* **Add Transit Gateway Routes to VPC Route Tables**
  ![alt text](image-9.png)
  ![alt text](image-10.png)
  ![alt text](image-11.png)
  ![alt text](image-12.png)
  ![alt text](image-13.png)
  ![alt text](image-14.png)
  ![alt text](image-15.png)
  ![alt text](image-16.png)
  ![alt text](image-17.png)
* **Create S3 Bucket**
  ![alt text](image-18.png)
  ![alt text](image-19.png)
  ![alt text](image-20.png)
  ![alt text](image-21.png)
* **Deploy infrastructure**
  ![alt text](image-22.png)
  ![alt text](image-23.png)
* **Create Backup plan**
  ![alt text](image-24.png)
  ![alt text](image-25.png)
* **Set up notifications**
  ![alt text](image-26.png)
* **Test Restores**
  ![alt text](image-27.png)
  ![alt text](image-28.png)
  ![alt text](image-29.png)
* **Create S3 Bucket**
  ![alt text](image-30.png)
* **Create EC2 for Storage Gateway**
  ![alt text](image-32.png)
  ![alt text](image-33.png)
* **Create Storage Gateway**
* **Configure SMB**

{{% notice warning %}}
**Important note:** Transit Gateway charges by the hour for each attachment. Delete resources in the correct order: **Attachments -> Transit Gateway -> CloudFormation Stack** to avoid leaving billable resources behind.
{{% /notice %}}
