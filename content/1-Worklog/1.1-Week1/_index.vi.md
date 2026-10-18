---
title: "Worklog Tuần 1"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

**Thời gian:** 05/10/2026 → 09/10/2026  
**Chủ đề:** Làm quen, AWS Account, Budgets, Support, IAM & VPC  
**Trạng thái:** Dự kiến

### Mục tiêu tuần 1:

* Làm quen với các thành viên FCAJ, nắm rõ nội quy và quy định đơn vị thực tập
* Tạo tài khoản AWS Free Tier an toàn, hiểu chiến lược credit và quản lý chi phí với AWS Budgets
* Tìm hiểu các gói hỗ trợ kỹ thuật AWS Support Plans và công cụ AWS Trusted Advisor
* Quản trị định danh và phân quyền truy cập với AWS IAM (User, Group, Policy, Role, MFA)
* Hiểu kiến trúc mạng cơ bản và thực hành triển khai Amazon VPC

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Làm quen với các thành viên FCAJ<br>- Đọc và lưu ý các nội quy, quy định tại đơn vị thực tập | 05/10/2026 | 05/10/2026 | |
| 3 | - Tạo AWS Free Tier account:<br>&nbsp;&nbsp;+ Chiến lược nhận đủ $200 credit và 5 nhiệm vụ kiếm credit<br>&nbsp;&nbsp;+ Danh sách sát thủ credit (credit killers) cần tránh<br>- Quản lý chi phí với AWS Budgets:<br>&nbsp;&nbsp;+ Tạo Cost Budget & Usage Budget<br>&nbsp;&nbsp;+ Thiết lập cảnh báo chi phí (Billing Alerts) gửi về email | 06/10/2026 | 06/10/2026 | <https://000001.awsstudygroup.com/> |
| 4 | - Tìm hiểu AWS Support Plans:<br>&nbsp;&nbsp;+ So sánh các gói Support: Basic, Developer, Business, Enterprise<br>&nbsp;&nbsp;+ Cách mở Support Case và kiểm tra tài khoản với AWS Trusted Advisor<br>- Quản trị danh tính với AWS IAM:<br>&nbsp;&nbsp;+ Khái niệm IAM User, IAM Group, IAM Policy<br>&nbsp;&nbsp;+ Thực hành tạo Admin Group & Admin User<br>&nbsp;&nbsp;+ Bật xác thực đa yếu tố (MFA) bảo vệ tài khoản | 07/10/2026 | 07/10/2026 | <https://000002.awsstudygroup.com/> |
| 5 | - Phân quyền nâng cao với IAM Role & Switch Role:<br>&nbsp;&nbsp;+ Tạo IAM Role và người dùng OperatorUser<br>&nbsp;&nbsp;+ Thực hành Switch Role từ OperatorUser sang Admin Role<br>&nbsp;&nbsp;+ Áp dụng nguyên tắc đặc quyền tối thiểu (Least Privilege)<br>- Tìm hiểu nền tảng mạng Amazon VPC:<br>&nbsp;&nbsp;+ Khái niệm VPC, CIDR block, Public Subnet vs Private Subnet<br>&nbsp;&nbsp;+ Route Table, Internet Gateway (IGW) & NAT Gateway<br>&nbsp;&nbsp;+ Tường lửa trong VPC: Security Group (Stateful) vs Network ACLs (Stateless) | 08/10/2026 | 08/10/2026 | <https://000003.awsstudygroup.com/> |
| 6 | - Thực hành triển khai hệ thống mạng Amazon VPC:<br>&nbsp;&nbsp;+ Khởi tạo Custom VPC với IPv4 CIDR Block<br>&nbsp;&nbsp;+ Tạo Public Subnet & Private Subnet<br>&nbsp;&nbsp;+ Tạo Internet Gateway (IGW) và gắn (attach) vào VPC<br>&nbsp;&nbsp;+ Cấu hình Route Table điều hướng traffic ra Internet qua IGW<br>&nbsp;&nbsp;+ Tạo Security Group cho phép traffic HTTP/SSH<br>- Review tổng quan kiến trúc tuần 1: Account → Budgets → Support → IAM → VPC<br>- Dọn dẹp tài nguyên (Clean up resources) | 09/10/2026 | 09/10/2026 | <https://000003.awsstudygroup.com/> |

### Kết quả dự kiến tuần 1:

* **Hòa nhập môi trường & Nắm vững nội quy:** Hoàn thành tốt quy trình tiếp nhận thực tập (onboarding) tại First Cloud Journey (FCAJ); nắm vững các quy định của công ty, tiêu chuẩn an toàn bảo mật thông tin, thời gian làm việc cùng lộ trình đào tạo và mục tiêu thực tập.
* **Thiết lập tài khoản AWS & Quản trị chi phí (Cost Governance):**
  * Đăng ký và kích hoạt thành công tài khoản AWS cá nhân theo chương trình AWS Free Tier.
  * Nắm vững chiến lược nhận tối đa $200 credit AWS và xác định các "sát thủ credit" (credit killers) để chủ động phòng ngừa phát sinh chi phí ngoài ý muốn.
  * Thiết lập AWS Budgets tự động (Cost Budget & Usage Budget) với các ngưỡng cảnh báo 80% và 100% được gửi thông báo qua email.
* **Hỗ trợ kỹ thuật & Kiểm tra tình trạng tài khoản:**
  * Hiểu rõ phạm vi hoạt động của các gói AWS Support Plans (Basic, Developer, Business, Enterprise) và thực hành tạo, quản lý Support Case thông qua AWS Support Center.
  * Sử dụng AWS Trusted Advisor để đánh giá tình trạng tài khoản theo các trụ cột cốt lõi: Tối ưu chi phí, Hiệu năng, Bảo mật, Khả năng chịu lỗi và Giới hạn dịch vụ.
* **Quản trị định danh và truy cập (AWS IAM):**
  * Nắm vững các thành phần cốt lõi của IAM: Users, Groups, Policies, Roles và cơ chế giới hạn quyền (permission boundaries).
  * Áp dụng nguyên tắc đặc quyền tối thiểu (Principle of Least Privilege) bằng cách tạo Admin Group và Admin User (non-root) phục vụ các tác vụ thường ngày, hạn chế tối đa việc sử dụng tài khoản root.
  * Kích hoạt xác thực đa yếu tố (MFA) bằng ứng dụng Authenticator ảo cho cả tài khoản root và IAM user.
  * Cấu hình IAM Role và thực hành thao tác Switch Role từ OperatorUser sang Admin Role, nắm rõ cơ chế chứng thực tạm thời (temporary security credentials).
* **Kiến trúc mạng đám mây (Amazon VPC):**
  * Nắm vững các khái niệm mạng trên AWS: dải địa chỉ IPv4 CIDR, Public Subnet (kết nối Internet) và Private Subnet (môi trường cô lập cho ứng dụng/dữ liệu).
  * Xây dựng và triển khai thành công một Custom VPC trên nhiều Availability Zone (AZ) nhằm đảm bảo tính sẵn sàng cao (High Availability).
  * Gắn kết Internet Gateway (IGW) và cấu hình Route Table để điều hướng chính xác lưu lượng truy cập Internet vào/ra VPC.
  * Phân biệt và ứng dụng hai lớp tường lửa trong VPC: Security Groups (Stateful - kiểm soát ở cấp độ máy chủ/instance) và Network ACLs (Stateless - kiểm soát ở cấp độ subnet).
  * Kiểm tra kết nối mạng end-to-end thành công, tạo nền tảng vững chắc cho việc triển khai máy chủ và cơ sở dữ liệu trong các tuần kế tiếp.
