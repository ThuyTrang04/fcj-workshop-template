---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---


### Mục tiêu tuần 7:
* Triển khai hệ thống lưu trữ tệp tin chuyên dụng doanh nghiệp với **Amazon FSx for Windows**.
* Làm chủ mô hình chia sẻ trách nhiệm và quản trị danh tính nâng cao với **IAM**, **Cognito** và **AWS Organizations**.
* Thiết lập cơ chế đăng nhập một lần (**SSO**) và quản lý chính sách bảo mật tập trung (**SCP**).
* Thực thi các tiêu chuẩn bảo mật quốc tế qua **AWS Security Hub** và mã hóa dữ liệu với **AWS KMS**.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2-3 | - Triển khai **Amazon FSx (Lab 000025)**: Thiết lập File Server Multi-AZ, cấu hình SMB và chống trùng lặp dữ liệu. <br> - Thực hành quản trị **IAM**: Tạo User/Group, áp dụng chính sách đặc quyền tối thiểu và sử dụng IAM Role. | 25/05/2026 | 26/05/2026 | Lab 000025 & AWS IAM |
| 4-5 | - Cấu hình **Amazon Cognito**: Thiết lập User Pool và Identity Pool để quản lý xác thực cho ứng dụng di động/web. <br> - Quản trị doanh nghiệp với **AWS Organizations**: Tạo OU và thiết lập **Service Control Policies (SCP)**. | 27/05/2026 | 28/05/2026 | Tài liệu AWS Security |
| 6 | - Triển khai **AWS Identity Center (SSO)** để quản lý truy cập tập trung. <br> - Thực hành mã hóa dữ liệu với **AWS KMS**: Quản lý Master Key và Data Key cho dữ liệu tại trạng thái nghỉ. | 29/05/2026 | 29/05/2026 | AWS Study Group |
| 7-CN | - Kích hoạt và cấu hình **AWS Security Hub (Lab 000018)** để đánh giá tuân thủ tiêu chuẩn CIS và AWS Best Practices. <br> - Tổng hợp hình ảnh thực hành, kiểm tra lỗi cấu hình và hoàn thiện báo cáo Tuần 7. | 30/05/2026 | 31/05/2026 | Lab 000018 & Cá nhân |

### Kết quả đạt được tuần 7:

* **Lưu trữ chuyên dụng & Quản trị danh tính:**
    * Triển khai thành công hệ thống tệp tin **Amazon FSx**, tối ưu hóa dung lượng qua Data Deduplication và đảm bảo an toàn với Shadow Copies.
    * Nắm vững cách chuyển đổi từ tài khoản Root sang hệ thống **IAM** phân quyền chặt chẽ, đảm bảo nguyên tắc bảo mật tối cao.
* **Quản trị quy mô lớn & Xác thực ứng dụng:**
    * Xây dựng được cấu trúc phân cấp doanh nghiệp qua **AWS Organizations**, kiểm soát quyền hạn tối đa của các tài khoản thành viên bằng **SCP**.
    * Hiểu rõ quy trình đăng ký và xác thực người dùng độc lập thông qua **Amazon Cognito**, giúp giảm tải cho backend ứng dụng.
* **Bảo mật tập trung & Mã hóa:**
    * Sử dụng **AWS KMS** để bảo vệ dữ liệu nhạy cảm, hiểu rõ cơ chế vận hành của hệ thống quản lý khóa trong môi trường Cloud.
    * Thiết lập thành công "trung tâm chỉ huy" **Security Hub**, giúp liên tục giám sát, phát hiện sớm lỗ hổng và đối chiếu với các tiêu chuẩn bảo mật quốc tế.
* **Create S3 Bucket:**
  ![alt text](image.png)
* **Create EC2 for Storage Gateway:**
  ![alt text](image-1.png)
* **Create Storage Gateway:**
  ![alt text](image-2.png)
  ![alt text](image-3.png)
  ![alt text](image-4.png)
  ![alt text](image-5.png)
* **Create File Shares**
  ![alt text](image-6.png)
* **Mount File shares on On-premises machine**
  ![alt text](image-7.png)
  ![alt text](image-8.png)
* **Create an SSD Multi-AZ file system**
  ![alt text](image-10.png)
* **Create an HHD Multi-AZ file system**
  ![alt text](image-11.png)
* **Create new file shares**
  ![alt text](image-12.png)
  ![alt text](image-13.png)
  ![alt text](image-14.png)
  ![alt text](image-15.png)
  ![alt text](image-16.png)
  ![alt text](image-17.png)
  ![alt text](image-18.png)
* **Test Performance**
  ![alt text](image-19.png)
  ![alt text](image-20.png)
* **DiskSpd Write tests**
  ![alt text](image-21.png)
* **fio read tests**
  ![alt text](image-22.png)
* **fio write  tests**
  ![alt text](image-23.png)
* **Monitor Performance**
* **Enable data deduplication**
* **Enable shadow copies**
* **Manage user sessions and open files**
* **Enable user storage quotas**
* **Enable Continuous Access share**
* **Scale throughput capacity**
* **Scale storage capacity**
* **Create S3 bucket**
  ![alt text](image-24.png)
* **Load data**
  ![alt text](image-25.png)
* **Enable static website feature**
  ![alt text](image-26.png)
* **Configuring public objects**
  ![alt text](image-27.png)
  ![alt text](image-28.png)
  ![alt text](image-29.png)
* **Block all public access**
  ![alt text](image-30.png)
* **Enable Security Hub**
  ![alt text](image-31.png)
  ![alt text](image-32.png)
* **Security Score by Standards**
  ![alt text](image-33.png)
  ![alt text](image-34.png)
