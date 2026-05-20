---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Mục tiêu tuần 9:
* Tăng cường bảo mật dữ liệu và quản lý quyền truy cập trên AWS thông qua **AWS KMS**, **IAM Policy**, **IAM Role** và cơ chế xác thực an toàn.
* Làm chủ kỹ thuật mã hóa dữ liệu, ghi nhận nhật ký hoạt động và giám sát truy cập bằng **AWS CloudTrail** và **Athena**.
* Áp dụng mô hình phân quyền hiện đại với **IAM Role**, giảm phụ thuộc vào Access Key và tăng cường bảo mật ứng dụng.
* Thực hành triển khai nguyên tắc **Least Privilege** và xây dựng môi trường AWS an toàn, dễ quản trị.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Triển khai **AWS KMS và mã hóa dữ liệu (Lab 000033)**: Tạo KMS Key và cấu hình mã hóa dữ liệu trên Amazon S3. <br> - Thực hành cấp quyền truy cập khóa mã hóa bằng IAM Policy. | 08/06/2026 | 08/06/2026 | Lab 000033 |
| 3 | - Tiếp tục cấu hình **CloudTrail** để ghi nhận hoạt động truy cập. <br> - Thực hiện truy vấn nhật ký bằng **Athena** và kiểm tra khả năng theo dõi truy cập tài nguyên. | 09/06/2026 | 09/06/2026 | Lab 000033 |
| 4 | - Thực hành **IAM nâng cao (Lab 000044)**: Tạo User, Group và IAM Role. <br> - Thiết lập Switch Role và kiểm thử phân quyền người dùng. | 10/06/2026 | 10/06/2026 | Lab 000044 |
| 5 | - Cấu hình điều kiện truy cập bằng **IAM Policy Conditions** và kiểm thử giới hạn quyền dựa trên IP hoặc điều kiện xác thực. | 11/06/2026 | 11/06/2026 | Lab 000044 |
| 6 | - Triển khai **IAM Role cho EC2 (Lab 000048)**: Tạo EC2 và cấp quyền truy cập Amazon S3 bằng IAM Role thay cho Access Key. | 12/06/2026 | 12/06/2026 | Lab 000048 |
| 7 | - Kiểm thử ứng dụng sử dụng IAM Role để truy cập S3. <br> - Đánh giá cơ chế cấp quyền động và kiểm tra tính bảo mật của hệ thống. | 13/06/2026 | 13/06/2026 | Lab 000048 |
| CN | - Tổng hợp hình ảnh thực hành, rà soát cấu hình IAM, KMS, CloudTrail và hoàn thiện báo cáo Tuần 9. | 14/06/2026 | 14/06/2026 | AWS Study Group & Cá nhân |

### Kết quả đạt được tuần 9:

* **Bảo mật dữ liệu & Mã hóa:**
    * Triển khai thành công **AWS KMS** để mã hóa dữ liệu lưu trữ trên Amazon S3, đảm bảo dữ liệu được bảo vệ trong quá trình lưu trữ và truy cập.
    * Hiểu rõ quy trình tạo, quản lý và phân quyền khóa mã hóa trong AWS.

* **Giám sát & Theo dõi hoạt động hệ thống:**
    * Sử dụng thành thạo **AWS CloudTrail** và **Athena** để ghi nhận, phân tích và truy vấn nhật ký hoạt động của hệ thống.
    * Tăng khả năng theo dõi truy cập và phát hiện hoạt động bất thường trong môi trường AWS.

* **Quản lý quyền truy cập & Bảo mật nâng cao:**
    * Thiết lập thành công **IAM User**, **IAM Role**, **Switch Role** và cơ chế kiểm soát quyền truy cập nâng cao.
    * Áp dụng hiệu quả nguyên tắc **Least Privilege**, giảm thiểu rủi ro lộ thông tin xác thực và nâng cao bảo mật hệ thống doanh nghiệp.

* **Triển khai mô hình cấp quyền hiện đại:**
    * Áp dụng **IAM Role cho EC2** để truy cập tài nguyên AWS mà không cần lưu trữ Access Key trong ứng dụng.
    * Hiểu rõ cơ chế xác thực tạm thời và phương pháp quản trị bảo mật theo tiêu chuẩn thực tế.
* **Create Policy and Role**
  ![alt text](image.png)
  ![alt text](image-1.png)
* **Create Group and User**
  ![alt text](image-2.png)
  ![alt text](image-4.png)
  ![alt text](image-5.png)
* **Create Key Management Service**
  ![alt text](image-6.png)
  ![alt text](image-7.png)
* **Create Amazon S3**
  ![alt text](image-8.png)
  ![alt text](image-9.png)
* **Create Bucket**
* **Upload data to S3**
* **Create AWS CloudTrail and Amazon Athena**
* 


