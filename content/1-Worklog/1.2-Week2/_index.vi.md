---
title: "Worklog Tuần 2"
date: 2026-04-22
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần này:
* Hoàn thành quy trình đăng ký, xác thực danh tính cho tài khoản AWS Free Tier.
* Triển khai các lớp bảo mật tối ưu (MFA) để bảo vệ tài khoản Root.
* Thực hành quản trị hệ thống chuyên nghiệp thông qua IAM (nhóm người dùng và phân quyền).

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Chuẩn bị thông tin cá nhân và thẻ thanh toán quốc tế. <br> - Thực hiện quy trình đăng ký tài khoản AWS Free Tier. | 20/04/2026 | 20/04/2026 | AWS Documentation |
| 3 | - Kích hoạt xác thực đa yếu tố (**MFA**) cho tài khoản Root. <br> - Tìm hiểu các nguy cơ bảo mật khi lộ mật khẩu. | 21/04/2026 | 21/04/2026 | AWS Security Blog |
| 4 | - Khởi tạo **Admin Group** và người dùng **IAM User**. <br> - Phân quyền truy cập hợp lý (Least Privilege). | 22/04/2026 | 22/04/2026 | AWS Study Group |
| 5 | - Khởi tạo và cấu hình **Access Keys** phục vụ truy cập qua CLI. <br> - Thực hành quản lý các chính sách bảo mật (Policies). | 23/04/2026 | 23/04/2026 | AWS Workshop |
| 6 | - Kiểm tra lại toàn bộ cấu hình bảo mật và hoàn thiện báo cáo thực hành. | 24/04/2026 | 24/04/2026 | Cá nhân |
| 7 | - Tìm hiểu về các gói hỗ trợ của AWS (Support Plans) | 25/04/2026 | 25/04/2026 | Cá nhân |


### Kết quả đạt được:

* **Về Bảo mật tài khoản:**
    * Đã tăng cường an toàn tuyệt đối cho tài khoản thông qua tính năng **MFA**, bảo vệ người dùng khỏi các nguy cơ lộ thông tin.
    * Hiểu rõ tầm quan trọng của việc không sử dụng tài khoản Root cho các hoạt động hàng ngày.
* **Về Quản trị hệ thống (IAM):**
    * Thành thạo kỹ năng tạo **Admin Group** và **IAM User** để quản lý nhân sự và tài nguyên đám mây một cách khoa học.
    * Nắm vững cách sử dụng **Access Keys** để vận hành tài nguyên qua dòng lệnh (CLI) một cách chuyên nghiệp.
    * Biết cách áp dụng các chính sách bảo mật để đảm bảo phân quyền đúng người, đúng việc.
* **Tạo **Admin Group** **Admin User** và **IAM User** :**
* ![alt text](image.png)
* ![alt text](image-1.png)
* ![alt text](image-2.png)
* ![alt text](image-3.png)
*  Creating Operator User
* ![alt text](image-4.png)
 ### Tìm hiểu về các gói hỗ trợ của AWS (Support Plans)

Bên cạnh việc thiết lập kỹ thuật, việc lựa chọn gói hỗ trợ phù hợp là yếu tố then chốt để đảm bảo hệ thống vận hành ổn định 24/7 dựa trên nhu cầu và ngân sách của doanh nghiệp.

#### Bốn cấp độ hỗ trợ chính:

| Gói dịch vụ | Đặc điểm nổi bật | Đối tượng phù hợp |
| :--- | :--- | :--- |
| **Basic** | Miễn phí, hỗ trợ mặc định về tài khoản, thanh toán và dịch vụ khách hàng. | Mọi đối tượng bắt đầu. |
| **Developer** | Cung cấp thêm các hướng dẫn về kiến trúc hệ thống và phản hồi nhanh hơn. | Môi trường thử nghiệm/phát triển. |
| **Business** | Hỗ trợ kiểm tra hệ thống tự động (Trusted Advisor) để tối ưu chi phí và bảo mật. | Hệ thống đang vận hành thực tế (Production). |
| **Enterprise** | Có chuyên gia quản lý kỹ thuật (TAM) hỗ trợ trực tiếp 24/7 cho các bài toán phức tạp. | Doanh nghiệp lớn, hệ thống quan trọng (Mission-critical). |

#### Kết quả nghiên cứu:
* **Tính linh hoạt:** AWS cho phép người dùng linh hoạt lựa chọn và thay đổi gói dịch vụ tùy theo giai đoạn phát triển của dự án.
* **Tài nguyên hỗ trợ:** Ngoài các kênh trực tiếp, AWS cung cấp hệ thống tài liệu kỹ thuật đồ sộ và diễn đàn cộng đồng chuyên sâu để giải quyết sự cố và tối ưu hóa hệ thống.
* **Giá trị cốt lõi:** Các gói dịch vụ không chỉ dừng lại ở việc sửa lỗi mà còn tập trung vào việc tư vấn kiến trúc và bảo mật lâu dài.

{{% notice tip %}}
**Lời khuyên:** Đối với sinh viên hoặc người mới bắt đầu như chúng ta, gói **Basic** kết hợp với việc tra cứu **AWS Documentation** là cách tốt nhất để học tập mà không phát sinh chi phí.
{{% /notice %}}
{{% notice warning %}}
**Ghi chú quan trọng:** Luôn lưu trữ Access Keys và thông tin MFA ở nơi an toàn. Tuyệt đối không chia sẻ các thông tin này lên các kho lưu trữ công khai như GitHub.
{{% /notice %}}