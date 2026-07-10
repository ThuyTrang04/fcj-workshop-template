---
title : "Các bước chuẩn bị"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---


## Overview

Trước khi bắt đầu triển khai hệ thống **AWS_OmniStay** trên nền tảng Amazon Web Services (AWS), người thực hiện cần chuẩn bị đầy đủ môi trường phát triển trên máy tính cá nhân cũng như cấu hình tài khoản AWS phục vụ cho quá trình triển khai hạ tầng.

Trong chương này, chúng ta sẽ tiến hành cài đặt các phần mềm cần thiết, cấu hình AWS CLI, tạo IAM User, thiết lập AWS Budget để kiểm soát chi phí và kiểm tra khả năng kết nối với tài khoản AWS.

Sau khi hoàn thành chương này, người thực hiện sẽ có đầy đủ môi trường để triển khai toàn bộ hệ thống AWS_OmniStay trong các chương tiếp theo.

---

## Learning Objectives

- Chuẩn bị môi trường phát triển cho dự án AWS_OmniStay.
- Cài đặt các công cụ phục vụ phát triển và triển khai ứng dụng.
- Tạo IAM User phục vụ triển khai hạ tầng.
- Cấu hình AWS Command Line Interface (AWS CLI).
- Thiết lập AWS Budget nhằm kiểm soát chi phí.
- Kiểm tra kết nối giữa máy tính và tài khoản AWS.

---

# Required Software

Bảng dưới đây liệt kê toàn bộ các phần mềm cần được cài đặt trước khi bắt đầu Workshop.

| Software | Version | Purpose |
|---|---|---|
| Windows 10/11 (64-bit) | Latest | Hệ điều hành |
| .NET SDK | 8 LTS | Phát triển ASP.NET Core Web API |
| AWS CLI | Version 2 | Quản lý tài nguyên AWS bằng dòng lệnh |
| Visual Studio Code | Latest | Chỉnh sửa mã nguồn |
| Git | Latest | Quản lý mã nguồn |
| Python | 3.12+ | Môi trường chạy Locust |
| DBeaver Community | Latest | Quản trị cơ sở dữ liệu MySQL |
| Locust | Latest | Kiểm thử tải hệ thống |

---

## Development Environment
Sau khi hoàn thành chương này, môi trường phát triển sẽ có cấu trúc như sau:

```text
+--------------------------------------------------+
          Local Development Environment
+--------------------------------------------------+
Visual Studio Code
.NET 8 SDK
Git
Python
AWS CLI
DBeaver
Locust

   |
   ▼
AWS IAM User

   |
   ▼
AWS Cloud (ap-southeast-1)

tt
















