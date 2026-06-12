---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Mục tiêu tuần 10:
* Tìm hiểu và triển khai các giải pháp phân tích dữ liệu trên AWS thông qua **Data Lake**, **AWS Glue**, **Amazon Athena** và **Amazon QuickSight**.
* Làm chủ cơ chế quản lý quyền truy cập nâng cao bằng **IAM Role**, **IAM Conditions** và kiểm soát truy cập theo IP/Time.
* Thực hành xây dựng hệ thống phân tích dữ liệu tập trung, hỗ trợ xử lý và trực quan hóa dữ liệu trên nền tảng Cloud.
* Nghiên cứu các giải pháp **Generative AI trên AWS** thông qua việc tích hợp **Amazon DynamoDB**, **Amazon OpenSearch Service** và **Amazon Bedrock**.
* Nâng cao khả năng quản trị bảo mật, giám sát dữ liệu và tối ưu quy trình phân tích dữ liệu doanh nghiệp trên AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|------|-----------|--------------|----------------|----------------|
| 2 | - Tìm hiểu tổng quan về **Data Lake trên AWS (Lab 000035)** và kiến trúc lưu trữ dữ liệu tập trung. <br> - Nghiên cứu vai trò của Amazon S3 trong hệ thống phân tích dữ liệu lớn và khả năng lưu trữ dữ liệu phi cấu trúc. | 15/06/2026 | 15/06/2026 | Lab 000035 |
| 3 | - Thực hành với **AWS Glue**: Tạo Database, Crawlers và xử lý dữ liệu tự động. <br> - Khám phá quy trình ETL và quản lý metadata trên AWS. <br> - Tìm hiểu cách AWS Glue hỗ trợ phân tích dữ liệu quy mô lớn. | 16/06/2026 | 16/06/2026 | Lab 000035 |
| 4 | - Thực hành truy vấn dữ liệu bằng **Amazon Athena** và trực quan hóa dữ liệu với **Amazon QuickSight**. <br> - Đánh giá hiệu quả phân tích dữ liệu serverless trên AWS Cloud. <br> - Xây dựng báo cáo dữ liệu và dashboard trực quan phục vụ phân tích nghiệp vụ. | 17/06/2026 | 17/06/2026 | Lab 000035 |
| 5 | - Thực hành **IAM Role & Conditions (Lab 000043)**: Tạo IAM User, Group và Role phục vụ phân quyền nâng cao. <br> - Thiết lập điều kiện truy cập theo IP Address và thời gian đăng nhập. <br> - Nghiên cứu cơ chế kiểm soát truy cập dựa trên chính sách IAM. | 18/06/2026 | 18/06/2026 | Lab 000043 |
| 6 | - Kiểm thử cơ chế **Switch Role** và đánh giá mô hình kiểm soát truy cập động trên AWS. <br> - Áp dụng nguyên tắc **Least Privilege** nhằm hạn chế truy cập ngoài phạm vi cho phép. <br> - Đánh giá hiệu quả của IAM Role trong môi trường doanh nghiệp. | 19/06/2026 | 19/06/2026 | Lab 000043 |
| 7 | - Tìm hiểu kiến trúc **Generative AI with DynamoDB Zero-ETL to OpenSearch Integration and Amazon Bedrock (Lab 000039)**. <br> - Nghiên cứu cơ chế đồng bộ dữ liệu bằng **Zero-ETL** từ DynamoDB sang OpenSearch. <br> - Tìm hiểu quy trình tạo Vector Embedding và Semantic Search bằng Amazon Bedrock. <br> - Đánh giá khả năng ứng dụng AI trong hệ thống phân tích dữ liệu hiện đại trên AWS. | 20/06/2026 | 20/06/2026 | Lab 000039 |
| CN | - Tổng hợp hình ảnh thực hành, rà soát cấu hình Glue, Athena, IAM, QuickSight và các thành phần AI trên AWS. <br> - Hoàn thiện báo cáo Tuần 10 và đánh giá hiệu quả triển khai hệ thống phân tích dữ liệu AWS. <br> - Tổng kết kiến thức về Data Analytics, IAM Security và Generative AI trên nền tảng AWS Cloud. | 21/06/2026 | 21/06/2026 | AWS Study Group & Cá nhân |

### Kết quả đạt được tuần 10:

#### Phân tích dữ liệu & Data Lake:
* Hiểu rõ kiến trúc **Data Lake** trên AWS và vai trò của Amazon S3 trong lưu trữ dữ liệu tập trung.
* Thực hành thành công với **AWS Glue**, nắm được quy trình ETL và cơ chế quản lý metadata tự động trong hệ thống dữ liệu lớn.
* Sử dụng **Amazon Athena** để truy vấn dữ liệu trực tiếp trên Amazon S3 mà không cần xây dựng hệ thống cơ sở dữ liệu riêng.
* Tìm hiểu và thực hành trực quan hóa dữ liệu với **Amazon QuickSight**, hỗ trợ xây dựng báo cáo và dashboard phục vụ ra quyết định.
* Hiểu được lợi ích của mô hình phân tích dữ liệu serverless trong việc tối ưu chi phí và khả năng mở rộng hệ thống.

#### Quản lý quyền truy cập & Bảo mật nâng cao:
* Thiết lập thành công **IAM User**, **IAM Group**, **IAM Role** và cơ chế **Switch Role** để quản lý truy cập linh hoạt trên AWS.
* Áp dụng điều kiện truy cập bằng **IAM Conditions** theo IP Address và thời gian đăng nhập nhằm tăng cường bảo mật hệ thống.
* Hiểu rõ cách triển khai nguyên tắc **Least Privilege** để hạn chế rủi ro truy cập trái phép trong môi trường doanh nghiệp.
* Nắm được cơ chế phân quyền động thông qua IAM Role và khả năng kiểm soát truy cập chi tiết bằng Policy Conditions.

#### Ứng dụng AI trong phân tích dữ liệu:
* Tìm hiểu kiến trúc tích hợp giữa **Amazon DynamoDB**, **Amazon OpenSearch Service** và **Amazon Bedrock** trong hệ thống Generative AI hiện đại.
* Hiểu được cơ chế **DynamoDB Zero-ETL Integration**, cho phép đồng bộ dữ liệu sang OpenSearch mà không cần xây dựng quy trình ETL truyền thống.
* Nắm được nguyên lý hoạt động của **Vector Embedding** và **Semantic Search** trong việc tìm kiếm dữ liệu theo ngữ nghĩa.
* Tìm hiểu vai trò của **Amazon Bedrock** trong việc xây dựng các ứng dụng AI tạo sinh (Generative AI) trên AWS.
* Đánh giá tiềm năng ứng dụng AI trong việc phân tích dữ liệu, tìm kiếm thông minh và hỗ trợ ra quyết định trong doanh nghiệp.

#### Tối ưu hệ thống dữ liệu trên Cloud:
* Nắm được quy trình quản lý và tối ưu dữ liệu trong môi trường AWS Cloud thông qua các dịch vụ phân tích dữ liệu hiện đại.
* Hiểu được cách kết hợp giữa Data Lake, Glue, Athena, QuickSight và các dịch vụ AI để xây dựng hệ thống dữ liệu tập trung.
* Đánh giá được khả năng mở rộng, hiệu suất xử lý và tính sẵn sàng cao của hệ thống dữ liệu doanh nghiệp trên AWS.
* Tăng cường kỹ năng triển khai, quản trị và bảo mật hệ thống dữ liệu trên nền tảng điện toán đám mây AWS.
* **Preparation Steps**
  ![alt text](image.png)
* **Data Collection and Storage Data Collection and Storage**
  ![alt text](image-1.png)
* **Create Data Catalog**
  ![alt text](image-2.png)
* **Data Transformation**
  ![alt text](image-3.png)
* **Analysis and visualization**
* **LHOL: Hands-on Labs for Amazon DynamoDB**
  ![alt text](image-4.png)
  ![alt text](image-5.png)
  ![alt text](image-6.png)
  ![alt text](image-7.png)
  ![alt text](image-8.png)
  ![alt text](image-9.png)
  ![alt text](image-10.png)
  ![alt text](image-11.png)
  ![alt text](image-13.png)
  ![alt text](image-14.png)
* **LBED: Generative AI with DynamoDB zero-ETL to OpenSearch integration and Amazon Bedrock**
* **Exercise 1: DynamoDB Capacity Units and Partitioning**
  ![alt text](image-15.png)
  ![alt text](image-16.png)
  ![alt text](image-17.png)
* **Exercise 2: Sequential and Parallel Table Scans**
  ![alt text](image-18.png)
* **Exercise 4: Global Secondary Index Key Overloading**
  ![alt text](image-19.png)
* **Exercise 5: Sparse Global Secondary Indexes.**
  ![alt text](image-20.png)
* **Exercise 6: Composite Keys**
  ![alt text](image-21.png)
* **Exercise 7: Adjacency Lists**
  ![alt text](image-22.png)
* **LCDC: Change Data Capture for Amazon DynamoDB**
  ![alt text](image-23.png)
* **LGME: Modeling Game Player Data with Amazon DynamoDB**
  ![alt text](image-24.png)
* **LEDA: Build a Serverless Event Driven Architecture with DynamoDB**
  ![alt text](image-25.png)

