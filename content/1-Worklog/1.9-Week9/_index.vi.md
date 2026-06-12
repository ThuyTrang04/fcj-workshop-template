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
* Tìm hiểu kiến thức nền tảng về cơ sở dữ liệu và các giải pháp lưu trữ trên AWS như **Amazon RDS** và **Amazon Aurora**.
* Áp dụng mô hình phân quyền hiện đại với **IAM Role**, giảm phụ thuộc vào Access Key và tăng cường bảo mật ứng dụng.
* Thực hành triển khai nguyên tắc **Least Privilege** và xây dựng môi trường AWS an toàn, dễ quản trị.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Triển khai **AWS KMS và mã hóa dữ liệu (Lab 000033)**: Tạo KMS Key và cấu hình mã hóa dữ liệu trên Amazon S3. <br> - Thực hành cấp quyền truy cập khóa mã hóa bằng IAM Policy. | 08/06/2026 | 08/06/2026 | Lab 000033 |
| 3 | - Tiếp tục cấu hình **CloudTrail** để ghi nhận hoạt động truy cập. <br> - Thực hiện truy vấn nhật ký bằng **Athena** và kiểm tra khả năng theo dõi truy cập tài nguyên. | 09/06/2026 | 09/06/2026 | Lab 000033 |
| 4 | - Tìm hiểu kiến thức nền tảng về cơ sở dữ liệu: **Primary Key**, **Foreign Key**, **Index**, sự khác biệt giữa **SQL** và **NoSQL**. <br> - Nghiên cứu mô hình xử lý dữ liệu **OLTP** và **OLAP** trong hệ thống doanh nghiệp. | 10/06/2026 | 10/06/2026 | AWS Database Overview |
| 5 | - Thực hành với **Amazon RDS** và **Amazon Aurora**: Tìm hiểu cơ chế quản trị tự động, sao lưu dữ liệu và triển khai **Multi-AZ**. <br> - Tối ưu hiệu năng và khả năng mở rộng của hệ thống dữ liệu Cloud. | 11/06/2026 | 11/06/2026 | AWS RDS & Aurora |
| 6 | - Thực hành **IAM nâng cao (Lab 000044)**: Tạo User, Group, IAM Role và thiết lập Switch Role. <br> - Triển khai **IAM Role cho EC2 (Lab 000048)** để truy cập S3 mà không cần Access Key. | 12/06/2026 | 12/06/2026 | Lab 000044 & Lab 000048 |
| 7 | - Thực hành kiến thức tổng quan về hệ thống cơ sở dữ liệu AWS từ **Lab 000005**: Tìm hiểu kiến trúc lưu trữ, cơ chế Backup, khả năng mở rộng và tối ưu dữ liệu. <br> - Đánh giá hiệu suất và khả năng đảm bảo tính sẵn sàng cao của hệ thống cơ sở dữ liệu trên Cloud. | 13/06/2026 | 13/06/2026 | Lab 000005 |
| CN | - Tổng hợp hình ảnh thực hành, rà soát cấu hình IAM, KMS, CloudTrail, RDS và hoàn thiện báo cáo Tuần 9. <br> - Đánh giá hiệu suất lưu trữ và khả năng bảo mật dữ liệu trong môi trường AWS. | 14/06/2026 | 14/06/2026 | AWS Study Group & Cá nhân |

### Kết quả đạt được tuần 9:

* **Bảo mật dữ liệu & Mã hóa:**
    * Triển khai thành công **AWS KMS** để mã hóa dữ liệu lưu trữ trên Amazon S3, đảm bảo dữ liệu được bảo vệ trong quá trình lưu trữ và truy cập.
    * Hiểu rõ quy trình tạo, quản lý và phân quyền khóa mã hóa trong AWS.

* **Giám sát & Theo dõi hoạt động hệ thống:**
    * Sử dụng thành thạo **AWS CloudTrail** và **Athena** để ghi nhận, phân tích và truy vấn nhật ký hoạt động của hệ thống.
    * Tăng khả năng theo dõi truy cập và phát hiện hoạt động bất thường trong môi trường AWS.

* **Kiến thức cơ sở dữ liệu & lưu trữ trên AWS:**
    * Nắm được các khái niệm nền tảng như **Primary Key**, **Foreign Key**, **Index**, cũng như sự khác biệt giữa mô hình **SQL** và **NoSQL**.
    * Tìm hiểu và thực hành với **Amazon RDS** và **Amazon Aurora**, hiểu rõ cơ chế **Automated Backup**, **Multi-AZ** và khả năng mở rộng toàn cầu của hệ thống dữ liệu AWS.
    * Hiểu rõ sự khác nhau giữa mô hình xử lý giao dịch **OLTP** và kho dữ liệu phân tích **OLAP**, từ đó lựa chọn kiến trúc phù hợp cho từng nhu cầu hệ thống.
    * Nắm vững vai trò của việc tối ưu thiết kế dữ liệu nhằm cải thiện hiệu suất, tính ổn định và khả năng mở rộng của ứng dụng thực tế. :contentReference[oaicite:0]{index=0}

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
* **Create AWS CloudTrail and Amazon Athena**
  ![alt text](image-10.png)
  ![alt text](image-11.png)
  ![alt text](image-12.png)
  ![alt text](image-13.png)
  ![alt text](image-14.png)
* **Create IAM Group**
  ![alt text](image-15.png)
* **Create IAM User**
  ![alt text](image-16.png)
  ![alt text](image-17.png)
* **Configure Role Condition**
  ![alt text](image-18.png)
  ![alt text](image-19.png)
  ![alt text](image-20.png)
* **IAM role on EC2**
  ![alt text](image-21.png)
* **Prerequisite Steps**
  ![alt text](image-22.png)
* **Create EC2 instance**
  ![alt text](image-23.png)
* **Create RDS database instance**
  ![alt text](image-24.png)
  ![alt text](image-25.png)
* **Application Deployment**
  ![alt text](image-26.png)
  ![alt text](image-27.png)



