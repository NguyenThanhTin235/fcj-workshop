---
title: "Worklog Tuần 1"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

**Thời gian:** 05/10/2026 → 09/10/2026  
**Chủ đề:** Làm quen, AWS Account, Budgets, Support, IAM & VPC  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 1:

* Hòa nhập đội ngũ FCAJ, nắm rõ nội quy và quy định thực tập
* Tạo tài khoản AWS Free Tier, quản lý credit và thiết lập cảnh báo chi phí với AWS Budgets
* Tìm hiểu AWS Support Plans và kiểm tra tài khoản với AWS Trusted Advisor
* Quản trị định danh với AWS IAM (User, Group, Policy, Role, MFA) và triển khai Amazon VPC

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Làm quen thành viên FCAJ<br>- Nắm nội quy, quy định tại đơn vị thực tập | 05/10/2026 | 05/10/2026 | |
| 3 | - Tạo AWS Free Tier account: chiến lược nhận $200 credit, 5 nhiệm vụ kiếm credit và tránh sát thủ credit<br>- Tạo Cost Budget & Usage Budget trên AWS Budgets, thiết lập cảnh báo email | 06/10/2026 | 06/10/2026 | <https://000001.awsstudygroup.com/> |
| 4 | - So sánh AWS Support Plans (Basic, Developer, Business, Enterprise), mở Support Case và dùng AWS Trusted Advisor<br>- Tạo Admin Group/User với AWS IAM và bật MFA | 07/10/2026 | 07/10/2026 | <https://000002.awsstudygroup.com/> |
| 5 | - Tạo IAM Role, OperatorUser và thực hành Switch Role theo nguyên tắc đặc quyền tối thiểu<br>- Tìm hiểu Amazon VPC: CIDR block, Public/Private Subnet, Route Table, IGW, NAT Gateway, Security Group vs Network ACLs | 08/10/2026 | 08/10/2026 | <https://000003.awsstudygroup.com/> |
| 6 | - Triển khai Custom VPC (IPv4 CIDR, Public/Private Subnet, IGW, Route Table, Security Group HTTP/SSH)<br>- Review kiến trúc tuần 1 (Account → Budgets → Support → IAM → VPC) và dọn dẹp tài nguyên | 09/10/2026 | 09/10/2026 | <https://000003.awsstudygroup.com/> |

---

### Kết quả đạt được tuần 1:

* **Hòa nhập & Tài khoản AWS:** Nắm vững nội quy First Cloud Journey; kích hoạt AWS Free Tier, hiểu chiến lược $200 credit và thiết lập AWS Budgets (ngưỡng 80%, 100%).
* **Hỗ trợ & Đánh giá hệ thống:** Phân biệt các gói AWS Support Plans, thực hành tạo Support Case và kiểm tra 5 trụ cột trên AWS Trusted Advisor.
* **AWS IAM:** Tạo Admin Group/User thay thế root, bật MFA, cấu hình IAM Role và thực hành Switch Role từ OperatorUser sang Admin Role.
* **Amazon VPC:** Triển khai Custom VPC đa AZ với Public/Private Subnet, IGW, Route Table, phân biệt Security Groups và Network ACLs, kiểm tra kết nối end-to-end thành công.
