---
title: "Week 4 Worklog"
date: 2026-04-05
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Use **CloudFormation** to automate deployment of complex network infrastructure.
* Set up a **Hybrid DNS** resolution system with **Route 53 Resolver**.
* Establish secure connectivity between AWS and on-premises environments through endpoints and rules.
* Practice inter-network connectivity with **VPC Peering** and control traffic with Security Groups/NACLs.

### Tasks to complete this week:

| Day | Task | Start date | Completion date | Reference |
| --- | ---- | ---------- | --------------- | --------- |
| 2-3 | - Create a **Key Pair** and use a CloudFormation template to quickly deploy a highly available network system. <br> - Configure Security Groups for Windows servers. | 04/05/2026 | 05/05/2026 | AWS Study Group |
| 4-5 | - Set up **Route 53 Resolver** with Inbound and Outbound Endpoints. <br> - Create Forwarding Rules to synchronize DNS between cloud and on-premises environments. | 06/05/2026 | 07/05/2026 | AWS Networking Guide |
| 6 | - Create **VPC Peering** to connect two virtual networks without using the public internet. <br> - Configure end-to-end routing between VPCs. | 08/05/2026 | 08/05/2026 | AWS Documentation |
| 7-Sun | - Test security with NACL and Security Group rules for cross-network traffic. <br> - Collect lab screenshots and complete the week 4 report. | 09/05/2026 | 10/05/2026 | Personal |

### Results achieved in week 4:

* **Automation and security:**
    * Practiced using **Key Pair** to connect securely to Windows servers.
    * Understood the power of **CloudFormation** for replicating network infrastructure with only a few lines of code.
* **Hybrid DNS system:**
    * Successfully configured **Route 53 Resolver**, allowing AWS resources to resolve on-premises servers and vice versa.
    * Understood how Inbound and Outbound Endpoints coordinate DNS requests.
* **Advanced connectivity:**
    * Successfully deployed **VPC Peering**, ensuring data moves between VPCs through AWS private networking for better speed and security.
    * Applied detailed permission controls to inter-network traffic through SG and NACL security layers.
* **Create Key Pair:**
  ![alt text](image.png)
* **Initialize CloudFormation template:**
  ![alt text](image-1.png)
  ![alt text](image-2.png)
* **Configure Security Group:**
  ![alt text](image-3.png)
* **Deploy Microsoft AD**
  ![alt text](image-6.png)
* **DNS setup:**
* **Create Route 53 Outbound Endpoint**
  ![alt text](image-4.png)
* **Create Route 53 Resolver Rules**
  ![alt text](image-5.png)
* **Create Route 53 Inbound Endpoints**
   ![alt text](image-7.png)
* **Initialize CloudFormation Templates**
  ![alt text](image-8.png)
  ![alt text](image-9.png)
* **Create Security Group**
  ![alt text](image-10.png)
  ![alt text](image-11.png)
* **Create EC2 Instance**
  ![alt text](image-12.png)
  ![alt text](image-13.png)
* **Update Network ACL**
  ![alt text](image-14.png)
  ![alt text](image-15.png)
* **Create VPC Peering**
  ![alt text](image-16.png)
* **Create Route Tables**
  ![alt text](image-17.png)
  ![alt text](image-18.png)
  ![alt text](image-19.png)
* **Cross-Peer DNS**
  ![alt text](image-20.png)
  ![alt text](image-21.png)

{{% notice info %}}
**Summary:** Week 4 shifted the mindset from managing individual resources to thinking in large-scale systems, cross-platform connectivity, and infrastructure automation, which are important steps for a professional Cloud Engineer.
{{% /notice %}}
