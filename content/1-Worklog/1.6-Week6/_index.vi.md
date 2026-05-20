---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
### Mục tiêu tuần 6:
* Xây dựng hạ tầng lưu trữ đối tượng bền vững với **Amazon S3** và triển khai website tĩnh.
* Làm chủ kỹ thuật thiết lập mạng cô lập nâng cao (**VPC**) với **Public/Private Subnets**, **NAT Gateway**.
* Cấu hình cơ chế bảo mật dữ liệu và kết nối an toàn qua **Versioning**, **Replication** và **VPC Endpoints**.
* Tìm hiểu chiến lược khắc phục sự cố sau thảm họa (**Disaster Recovery**) và quản lý sao lưu tập trung với **AWS Backup**.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2-3 | - Khởi tạo **S3 Bucket**, cấu hình **Static Website Hosting** và tích hợp **CloudFront**. <br> - Thiết lập **Bucket Policy** để quản lý quyền truy cập công khai an toàn. | 18/05/2026 | 19/05/2026 | Lab S3 (000057) |
| 4-5 | - Cấu hình **VPC nâng cao**: Phân chia Subnet, thiết lập Internet Gateway và NAT Gateway. <br> - Triển khai **VPC Endpoints** để kết nối nội bộ với S3 không qua internet. | 20/05/2026 | 21/05/2026 | Lab VPC (000013-14) |
| 6 | - Thực hành **Versioning** và **Multi-Region Replication** để đảm bảo tính sẵn sàng cao. <br> - Kiểm soát lưu lượng mạng qua các tầng bảo mật **NACLs** và **Security Groups**. | 22/05/2026 | 22/05/2026 | AWS Study Group |
| 7-CN | - Thiết lập kế hoạch sao lưu tập trung với **AWS Backup**. <br> - Tổng hợp hình ảnh thực hành và hoàn thiện báo cáo Tuần 6. | 23/05/2026 | 24/05/2026 | Cá nhân |

### Kết quả đạt được tuần 6:

* **Lưu trữ & Phân phối nội dung:**
    * Triển khai thành công Website tĩnh tối ưu hóa tốc độ toàn cầu bằng cách kết hợp **S3** và **CloudFront**.
    * Nắm vững cách quản lý vòng đời đối tượng và các lớp lưu trữ (**Storage Classes**) để tối ưu chi phí.
* **Quản trị mạng nâng cao:**
    * Xây dựng hệ thống mạng cô lập an toàn, cho phép máy chủ trong Private Subnet truy cập internet thông qua **NAT Gateway** mà vẫn đảm bảo tính bảo mật.
    * Triển khai **VPC Peering** và **VPC Endpoints**, giúp tối ưu hóa đường truyền dữ liệu nội bộ trên nền tảng AWS.
* **Bảo mật & Tính sẵn sàng cao:**
    * Hiểu rõ các chỉ số **RTO/RPO** và chiến lược khắc phục thảm họa thông qua việc sao chép dữ liệu đa vùng.
    * Sử dụng thành thạo **AWS Backup** để quản lý sao lưu đa dịch vụ từ một giao diện duy nhất.
* **Create S3 bucket**
  ![alt text](image.png)
* **Upload Data**
  ![alt text](image-1.png)
  ![alt text](image-2.png)
* **Enable static website feature**
  ![alt text](image-3.png)
### Kết quả đạt được :
  * Thùng chứa của bạn hiện đã có URL điểm cuối trang web.
  * S3 sẽ sử dụng index.html làm trang mặc định.
  * Thùng chứa này được cấu hình để lưu trữ nội dung tĩnh.
  * Bạn đã sẵn sàng tải lên các tệp trang web.
* **Configuring public access block**
   ![alt text](image-4.png)
   ![alt text](image-5.png)
   ![alt text](image-6.png)
### Kết quả đạt được :
  * Đã bật ACL trên nhóm lưu trữ S3 của bạn
  * Đã cấu hình cài đặt quyền sở hữu đối tượng phù hợp
  * Cho phép truy cập công khai các đối tượng trên trang web
  * Đã chuẩn bị bucket của bạn để lưu trữ website tĩnh
* **Test website**
  ![alt text](image-7.png)
* **Block all public access**
  ![alt text](image-8.png)
  ![alt text](image-9.png)
* **Config Amazon CloudFront**
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
**Tóm tắt:** Tuần 6 giúp hoàn thiện tư duy của một Cloud Engineer trong việc kết hợp giữa khả năng lưu trữ không giới hạn của S3 và sự linh hoạt, bảo mật của VPC. Đây là nền tảng cốt lõi để xây dựng các ứng dụng có quy mô lớn và độ tin cậy cao trên AWS.
{{% /notice %}}

