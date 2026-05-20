---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---


### Mục tiêu tuần 8:
* Tối ưu chi phí và tự động hóa quản lý tài nguyên trên AWS thông qua **AWS Lambda**, **CloudWatch** và cơ chế quản lý vòng đời tài nguyên.
* Làm chủ kỹ thuật quản lý tài nguyên bằng **Resource Tags**, **Resource Groups** và kiểm soát quyền truy cập nâng cao.
* Áp dụng cơ chế phân quyền bằng **IAM Policy**, **Resource Tags** và **IAM Permission Boundary**.
* Nâng cao khả năng quản trị, kiểm soát bảo mật và triển khai nguyên tắc **Least Privilege** trong AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Triển khai **Tối ưu chi phí EC2 (Lab 000022)**: Sử dụng **AWS Lambda** kết hợp **CloudWatch Events** để tự động bật/tắt EC2 theo lịch trình. <br> - Tạo IAM Role cho Lambda và kiểm tra hoạt động hệ thống. | 01/06/2026 | 01/06/2026 | Lab 000022 |
| 3 | - Tiếp tục kiểm thử và xác minh cơ chế tự động hóa EC2. <br> - Thực hiện xử lý lỗi, theo dõi log qua CloudWatch và tối ưu quy trình vận hành. | 02/06/2026 | 02/06/2026 | Lab 000022 |
| 4 | - Thực hành **Resource Tags và Resource Groups (Lab 000027)**: Gắn thẻ cho EC2, S3, VPC và nhóm tài nguyên theo tiêu chí quản lý. | 03/06/2026 | 03/06/2026 | Lab 000027 |
| 5 | - Thực hành **IAM Policy kết hợp Resource Tags (Lab 000028)**: Thiết lập điều kiện kiểm soát truy cập dựa trên Tags. <br> - Kiểm thử phân quyền theo nguyên tắc đặc quyền tối thiểu. | 04/06/2026 | 04/06/2026 | Lab 000028 |
| 6 | - Triển khai **IAM Permission Boundary (Lab 000030)**: Tạo Policy giới hạn quyền EC2 theo Region. <br> - Áp dụng Permission Boundary cho IAM User và kiểm thử khả năng truy cập. | 05/06/2026 | 05/06/2026 | Lab 000030 |
| 7 | - Xác minh hoạt động của **Permission Boundary**, kiểm tra giới hạn quyền tại các Region khác nhau. <br> - Đánh giá hiệu quả kiểm soát truy cập và bảo mật tài nguyên AWS. | 06/06/2026 | 06/06/2026 | Lab 000030 |
| CN | - Tổng hợp hình ảnh thực hành, kiểm tra lỗi cấu hình, rà soát tài nguyên và hoàn thiện báo cáo Tuần 8. | 07/06/2026 | 07/06/2026 | AWS Study Group & Cá nhân |

### Kết quả đạt được tuần 8:

* **Tối ưu chi phí & Tự động hóa:**
    * Triển khai thành công cơ chế tự động bật/tắt **Amazon EC2** bằng **AWS Lambda**, giúp giảm thời gian quản trị thủ công và tối ưu chi phí sử dụng tài nguyên.
    * Hiểu rõ sự phối hợp giữa **Lambda**, **CloudWatch** và **IAM Role** trong quy trình tự động hóa tài nguyên AWS.

* **Quản lý tài nguyên & Phân loại hệ thống:**
    * Sử dụng thành thạo **Resource Tags** và **Resource Groups** để tổ chức tài nguyên theo môi trường và mục đích sử dụng.
    * Xây dựng quy trình quản lý tài nguyên tập trung, hỗ trợ vận hành hiệu quả trong hệ thống lớn.

* **Kiểm soát quyền truy cập & Bảo mật nâng cao:**
    * Thiết lập thành công **IAM Policy** theo điều kiện Tags và triển khai **IAM Permission Boundary** để giới hạn quyền tối đa người dùng.
    * Hiểu rõ cách áp dụng nguyên tắc **Least Privilege**, tăng cường kiểm soát truy cập và giảm thiểu rủi ro bảo mật trong doanh nghiệp.
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
* **Check Resultz**
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
* **Proceed to create EC2 instance when there are no and qualified Tags**
  ![alt text](image-25.png)
* **Edit Resource Tag on EC2 Instance**
  ![alt text](image-26.png)
* **Create Restriction Policy**
  ![alt text](image-27.png)
* **Create IAM Limited User**
  ![alt text](image-28.png)
* **Test IAM User Limits**
  ![alt text](image-29.png)


