---
title: "Worklog Tuần 3"
date: 2026-04-25
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Hiểu rõ khái niệm và cách thiết lập **Amazon VPC** để tạo môi trường mạng ảo riêng biệt.
* Thành thạo kỹ năng quản lý IP, phân chia Subnet và cấu hình định tuyến (Route Table).
* Triển khai các lớp bảo mật mạng: **Security Groups** và **Network ACLs**.
* Tìm hiểu các phương thức kết nối internet và hạ tầng Hybrid (Internet Gateway, NAT Gateway, VPN).
* Nghiên cứu các giải pháp nâng cao như VPC Peering và Load Balancing (ELB).
* Triển khai các thành phần điều phối mạng: **Subnet**, **Internet Gateway**, và **Route Table**.
* Quản trị máy chủ **EC2** an toàn qua **NAT Gateway** và **Instance Connect Endpoint**.
### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu tổng quan về VPC, dải địa chỉ IP (CIDR) và cách chia Subnet. <br> - Cấu hình Route Table cho lưu lượng nội bộ. | 27/04/2026 | 27/04/2026 | AWS Networking Guide |
| 3 | - Thiết lập kết nối Internet qua **Internet Gateway** (Public Subnet). <br> - Cấu hình **NAT Gateway** để cho phép Private Subnet ra ngoài internet. | 28/04/2026 | 28/04/2026 | AWS Documentation |
| 4 | - Thực hành bảo mật: Cấu hình **Security Groups** (Stateful) và **NACLs** (Stateless). <br> - Phân biệt cơ chế hoạt động của 2 lớp bảo mật này. | 29/04/2026 | 29/04/2026 | Security Essentials |
| 5 | - Nghiên cứu kết nối nâng cao: **VPC Peering**, **VPN** và **Transit Gateway**. <br> - Tìm hiểu về **Elastic Load Balancing (ELB)** để tăng độ sẵn sàng. <br> - Phân biệt Security Group (Stateful) và Network ACL (Stateless). | 30/04/2026 | 30/04/2026 | AWS Study Group |
| 6 | - **Thực hành nâng cao:** Cấu hình **NAT Gateway** cho Private Subnet. <br> - Thiết lập **EC2 Instance Connect Endpoint** để quản trị từ xa an toàn. | 1/05/2026 | 1/05/2026 | AWS Workshop |

### Kết quả đạt được tuần 3:

* **Về Tư duy hệ thống mạng:**
    * Có khả năng thiết lập một môi trường mạng ảo riêng biệt, an toàn trên đám mây.
    * Nắm vững cách kiểm soát lưu lượng truy cập ra/vào thông qua hai lớp phòng thủ (SG và NACL).
* **Về Kỹ năng triển khai:**
    * Biết cách kết nối tài nguyên đám mây với internet hoặc hạ tầng tại chỗ (On-premise) thông qua VPN/Direct Connect.
    * Hiểu phương pháp tối ưu hóa khả năng mở rộng của ứng dụng bằng cách sử dụng bộ cân bằng tải (Load Balancer).
    * Có kỹ năng xử lý các sự cố cơ bản liên quan đến kết nối và định tuyến trong VPC.
* **Create VPC:**
  ![alt text](image.png)
* **Create Subnet:**
  ![alt text](image-1.png)
* **Create Internet gateways :**
  ![alt text](image-2.png)
* **Create Route tables :**
  ![alt text](image-3.png)
* **Create Security Groups  :** 
  ![alt text](image-4.png)
* **Create EC2  :** 
  ![alt text](image-5.png)
  ![alt text](image-6.png)
  ![alt text](image-7.png)
  ![alt text](image-8.png)
  ![alt text](image-9.png)
  ![alt text](image-10.png)
  ![alt text](image-11.png)
  ![alt text](image-12.png)
  ![alt text](image-13.png)
* **Create NAT Gateways :** 
  ![alt text](image-14.png)
  ![alt text](image-15.png)
  ![alt text](image-16.png)
  ![alt text](image-17.png)
  ![alt text](image-18.png)
  ![alt text](image-19.png)
* **Create EC2 Instance Connect Endpoint :** 
  ![alt text](image-20.png)
  ![alt text](image-21.png)
  ![alt text](image-22.png)
{{% notice success %}}
**Tóm tắt:** Việc làm chủ VPC giúp xây dựng nền tảng vững chắc để triển khai các dịch vụ khác như EC2, RDS một cách an toàn và tối ưu nhất.
{{% /notice %}}

