---
title: "Các bài blogs đã dịch"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Trong quá trình thực tập và tìm hiểu về nền tảng **Amazon Web Services (AWS)**, em đã nghiên cứu và tổng hợp một số bài viết liên quan đến thiết kế kiến trúc, triển khai ứng dụng và các kinh nghiệm thực tế khi làm việc với môi trường điện toán đám mây. Các bài blog dưới đây được xây dựng dựa trên quá trình học tập, thực hành và tham khảo tài liệu chính thức của AWS nhằm giúp củng cố kiến thức, rèn luyện tư duy thiết kế hệ thống cũng như hiểu rõ hơn về các nguyên tắc triển khai trên nền tảng Cloud.

Mỗi bài viết tập trung vào một chủ đề khác nhau, từ quy trình thiết kế kiến trúc hệ thống, các nguyên tắc bảo mật, lựa chọn dịch vụ AWS phù hợp cho đến những kinh nghiệm thực tế và các sai lầm thường gặp khi triển khai ứng dụng. Đây là những kiến thức có giá trị giúp người học tiếp cận AWS theo hướng thực tế và có thể áp dụng vào các dự án sau này.

---

### [Blog 1 - Từ yêu cầu đến kiến trúc: Quy trình thiết kế một hệ thống web trên AWS](3.1-Blog1/)

Bài viết trình bày quy trình thiết kế kiến trúc cho một hệ thống web trên AWS, bắt đầu từ việc phân tích yêu cầu của hệ thống đến lựa chọn các dịch vụ phù hợp như **Amazon VPC, Amazon EC2, Amazon RDS, Amazon S3, Application Load Balancer** và **AWS IAM**. Bên cạnh đó, bài viết còn chia sẻ các quyết định thiết kế quan trọng liên quan đến phân chia **Public/Private Subnet**, bảo mật hệ thống, khả năng mở rộng, tính sẵn sàng cao và tối ưu chi phí khi triển khai ứng dụng trên nền tảng AWS.

---

### [Blog 2 - 7 sai lầm người mới thường gặp khi triển khai ứng dụng web đầu tiên trên AWS](3.2-Blog2/)

Bài viết tổng hợp những sai lầm phổ biến mà người mới thường gặp khi triển khai ứng dụng trên AWS như đặt sai vị trí tài nguyên trong VPC, cấu hình **Security Group** chưa hợp lý, sử dụng **Access Key** thay cho **IAM Role**, lưu trữ dữ liệu chưa đúng cách, hiểu chưa rõ về **Region**, **Availability Zone** và **VPC**, cũng như chưa thực hiện giám sát hệ thống bằng **Amazon CloudWatch**. Đồng thời, bài viết cũng đưa ra các khuyến nghị và **AWS Best Practices** nhằm giúp xây dựng hệ thống an toàn, dễ quản lý và có khả năng mở rộng trong thực tế.

---

### [Blog 3 - 7 cách giúp tối ưu chi phí khi triển khai ứng dụng trên AWS](3.3-Blog3/)

Bài viết chia sẻ những kinh nghiệm thực tế giúp tối ưu chi phí khi sử dụng AWS, từ việc lựa chọn đúng dịch vụ và cấu hình tài nguyên, tận dụng **AWS Free Tier**, quản lý vòng đời dữ liệu trên **Amazon S3**, theo dõi chi phí bằng **AWS Budgets** và **AWS Cost Explorer**, cho đến việc dọn dẹp các tài nguyên không còn sử dụng. Bên cạnh đó, bài viết cũng giới thiệu nguyên tắc **Start Simple, Scale Later** và trụ cột **Cost Optimization** trong **AWS Well-Architected Framework**, giúp người đọc xây dựng hệ thống vừa đáp ứng yêu cầu kỹ thuật vừa sử dụng hiệu quả ngân sách khi triển khai trên nền tảng AWS.

---