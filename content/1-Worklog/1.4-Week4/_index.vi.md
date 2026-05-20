---
title: "Worklog Tuần 4"
date: 2026-04-05
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:
* Sử dụng **CloudFormation** để tự động hóa việc triển khai hạ tầng mạng phức tạp.
* Thiết lập hệ thống phân giải tên miền lai (**Hybrid DNS**) với **Route 53 Resolver**.
* Kết nối an toàn giữa môi trường AWS và nội bộ (On-premises) thông qua Endpoints và Rules.
* Thực hành kết nối liên mạng bằng **VPC Peering** và kiểm soát lưu lượng bằng Security Group/NACL.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2-3 | - Tạo **Key Pair** và sử dụng CloudFormation Template để triển khai nhanh hệ thống mạng sẵn sàng cao. <br> - Cấu hình Security Group cho các máy chủ Windows. | 04/05/2026 | 05/05/2026 | AWS Study Group |
| 4-5 | - Thiết lập **Route 53 Resolver**: Cấu hình Inbound/Outbound Endpoints. <br> - Tạo Forwarding Rules để đồng bộ DNS giữa Cloud và On-premises. | 06/05/2026 | 07/05/2026 | AWS Networking Guide |
| 6 | - Khởi tạo **VPC Peering** để kết nối 2 mạng ảo mà không qua internet công cộng. <br> - Cấu hình định tuyến xuyên suốt giữa các VPC. | 08/05/2026 | 08/05/2026 | AWS Documentation |
| 7-CN | - Kiểm tra bảo mật với NACL và Security Group cho lưu lượng liên mạng. <br> - Tổng hợp hình ảnh thực hành và hoàn thiện báo cáo Tuần 4. | 09/05/2026 | 10/05/2026 | Cá nhân |

### Kết quả đạt được tuần 4:

* **Tự động hóa & Bảo mật:**
    * Làm chủ kỹ thuật sử dụng **Key Pair** để kết nối an toàn vào máy chủ Windows.
    * Hiểu sức mạnh của **CloudFormation** trong việc nhân bản hạ tầng mạng chỉ với vài dòng code.
* **Hệ thống DNS lai (Hybrid DNS):**
    * Cấu hình thành công **Route 53 Resolver**, giúp các tài nguyên trên AWS có thể tìm thấy các máy chủ trong mạng nội bộ và ngược lại.
    * Nắm vững cách vận hành Inbound/Outbound Endpoints để điều phối yêu cầu DNS.
* **Kết nối nâng cao:**
    * Triển khai thành công **VPC Peering**, đảm bảo dữ liệu di chuyển giữa các VPC trên đường truyền nội bộ của AWS, tăng tốc độ và bảo mật.
    * Phân quyền chi tiết cho lưu lượng mạng liên vùng thông qua các lớp bảo mật SG và NACL.
* **Tạo Cặp khóa:**
  ![alt text](image.png)
* **Khởi tạo mẫu cloudFormation:**
  ![alt text](image-1.png)
  ![alt text](image-2.png)
* **Cấu hình Configure Security Group:**
  ![alt text](image-3.png) 
* **Triển khai Microsoft AD**
  ![alt text](image-6.png)
* **Thiết Lập DNS:**
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
**Tóm tắt:** Tuần 4 giúp chuyển đổi từ việc quản lý đơn lẻ sang tư duy hệ thống quy mô lớn, kết nối đa nền tảng và tự động hóa hạ tầng — những bước đi quan trọng của một Cloud Engineer chuyên nghiệp.
{{% /notice %}}


