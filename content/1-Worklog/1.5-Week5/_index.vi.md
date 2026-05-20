---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
### Mục tiêu tuần 5:
* Triển khai kiến trúc mạng hình sao (Hub-and-Spoke) bằng **AWS Transit Gateway (TGW)** để kết nối đa VPC.
* Thành thạo kỹ thuật **Infrastructure as Code (IaC)** với CloudFormation để khởi tạo hạ tầng phức tạp.
* Tìm hiểu sâu về kiến trúc **Amazon EC2**: Phân biệt các loại Chip (Intel, AMD, Graviton) và hệ thống ảo hóa Nitro.
* Quản lý lưu trữ hiệu quả giữa **EBS (Bền vững)** và **Instance Store (Tốc độ cao)**.
* Tự động hóa cấu hình máy chủ bằng **User Data** và quản lý thông tin qua **Metadata**.
* Thiết lập kết nối **S3 VPC Endpoints** và **Hybrid DNS** để bảo mật dữ liệu và đồng bộ hóa phân giải tên miền.
* Nghiên cứu dịch vụ di trú **AWS MGN** và chiến lược phục hồi sau thảm họa (**Disaster Recovery**).
  
### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2-3 | - Sử dụng CloudFormation khởi tạo 4 VPC và hệ thống máy chủ mẫu. <br> - Thiết lập **Transit Gateway**, Attachments và quy hoạch bảng định tuyến TGW. | 11/05/2026 | 12/05/2026 | AWS Module 02 |
| 4 | - Cấu hình định tuyến VPC và kiểm tra kết nối liên thông giữa các Private Subnet. <br> - Sử dụng **Reachability Analyzer** để phân tích luồng gói tin. | 13/05/2026 | 13/05/2026 | AWS Module 02 |
| 5 | - Nghiên cứu về EC2 Instance Types, Chip Graviton và lợi ích của ảo hóa Nitro. <br> - Phân biệt cơ chế sao lưu Snapshot (Full vs Incremental). | 14/05/2026 | 14/05/2026 | AWS Module 03 |
| 6 | - Thực hành cấu hình **User Data** để tự động cài đặt Web Server. <br> - Thử nghiệm truy vấn **Metadata** qua địa chỉ IP nội bộ `169.254.169.254`.<br> - Tìm hiểu cơ chế **Auto Scaling** để tự động co giãn số lượng máy ảo.<br>- Cấu hình **S3 Gateway Endpoint** và **Interface Endpoint (PrivateLink)** để truy cập S3 nội bộ. <br> - Thiết lập VPN giả lập và DNS để hỗ trợ kết nối riêng tư từ On-premise đến S3. | 15/05/2026 | 15/05/2026 | AWS Module 03 |
| 7-CN | - So sánh hiệu năng và độ an toàn dữ liệu giữa **EBS** và **Instance Store**. <br>- Triển khai máy chủ tối giản với **Amazon Lightsail** và thiết lập chia sẻ tệp qua **EFS/FSx**. <br> - Nghiên cứu dịch vụ di trú **AWS MGN** và chiến lược phục hồi sau thảm họa (Disaster Recovery). <br> - **Clean up:** Xóa TGW Attachments, TGW và CloudFormation Stack để tránh phí. | 16/05/2026 | 17/05/2026 | Cá nhân |


### Kết quả đạt được tuần 5:

* **Về Kiến trúc mạng lưới (Networking):**
    * Thay thế được mô hình VPC Peering phức tạp bằng **Transit Gateway**, giúp quản lý tập trung và dễ mở rộng.
    * Biết cách sử dụng Bastion Host để SSH vào các máy chủ trong mạng nội bộ một cách an toàn.
* **Về Tài nguyên tính toán (Compute & Storage):**
    * Nắm vững cách tối ưu chi phí bằng việc chọn đúng loại Instance và tận dụng chip ARM Graviton.
    * Hiểu rõ rủi ro mất dữ liệu trên **Instance Store** và tính bền vững của **EBS** (nhân bản dữ liệu tại 3 node trong 1 AZ).
    * Tự động hóa được quy trình triển khai phần mềm ngay khi máy chủ vừa khởi tạo nhờ User Data.
* **Tối ưu hóa kết nối:** Thay thế mô hình Peering phức tạp bằng Transit Gateway và bảo mật dữ liệu S3 tuyệt đối qua VPC Endpoints.
* **Generate Key Pair**
  ![alt text](image.png)
* **Create Initialize CloudFormation Template**
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
* **Cấu hình SMB**
  
{{% notice warning %}}
**Lưu ý quan trọng:** Transit Gateway tính phí theo giờ cho mỗi Attachment. Phải xóa theo đúng thứ tự: **Attachments -> Transit Gateway -> CloudFormation Stack** để đảm bảo không bị sót tài nguyên gây tốn phí.
{{% /notice %}}





