---
title: "Worklog Tuần 7"
date: 2026-10-05
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

**Thời gian:** 16/11/2026 → 20/11/2026  
**Chủ đề:** Remote Server Access với Systems Manager Session Manager & Infrastructure as Code (CloudFormation, AWS CDK)  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 7:

* Thực hành truy cập an toàn vào các EC2 instance (Public & Private) không cần SSH key hay Bastion Host bằng AWS Systems Manager Session Manager, VPC Endpoints, lưu log phiên lên S3 và Port Forwarding
* Triển khai và quản lý hạ tầng dưới dạng mã (IaC) với AWS CloudFormation (Template cơ bản, Custom Resources kết hợp Lambda, Mappings, StackSets và Drift Detection)
* Xây dựng, cập nhật và triển khai hạ tầng AWS bằng ngôn ngữ lập trình với AWS CDK (Essentials & Advanced: ECS/ALB/API Gateway, Lambda/S3 và Nested Stacks)

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Chuẩn bị VPC, Public/Private Subnet, Security Group, EC2 Linux/Windows và IAM Role cho SSM<br>- Kết nối EC2 Public và Private qua Session Manager bằng VPC Endpoints (`ssm`, `ssmmessages`, `ec2messages`)<br>- Cấu hình lưu Session Logs lên S3 qua S3 Gateway Endpoint, thực hành Port Forwarding và dọn dẹp tài nguyên | 16/11/2026 | 16/11/2026 | <https://000058.awsfcaj.com/> |
| 3 | - Tạo IAM User, khởi chạy AWS CloudShell và viết/triển khai CloudFormation Template cơ bản<br>- Thực hành CloudFormation nâng cao: Custom Resources với AWS Lambda, Mappings và StackSets<br>- Kiểm tra sai lệch cấu hình với Drift Detection và dọn dẹp Stack | 17/11/2026 | 17/11/2026 | <https://000037.awsfcaj.com/> |
| 4 | - Thiết lập workspace CDK và môi trường AWS CloudShell cho bài lab AWS CDK Essentials<br>- Khởi tạo dự án CDK, tìm hiểu Constructs/Stacks và tạo CDK Template ban đầu | 18/11/2026 | 18/11/2026 | <https://000038.awsfcaj.com/> |
| 5 | - Biên dịch template (`cdk synth`), triển khai (`cdk deploy`), kiểm tra thay đổi và cập nhật CDK Template (`cdk diff`)<br>- Dọn dẹp tài nguyên bài lab CDK Essentials và hệ thống hóa quy trình IaC | 19/11/2026 | 19/11/2026 | <https://000038.awsfcaj.com/> |
| 6 | - Chuẩn bị IAM Role, EC2 instance và cấu hình VSCode cho bài lab AWS CDK Advanced<br>- Triển khai kiến trúc đa dịch vụ với CDK: ECS + ALB + API Gateway, Lambda + S3 và Nested Stacks<br>- Tổng kết tuần 7 và dọn dẹp toàn bộ stack/tài nguyên lab | 20/11/2026 | 20/11/2026 | <https://000076.awsfcaj.com/> |

---

### Kết quả đạt được tuần 7:

* **Truy cập máy chủ an toàn (AWS Systems Manager Session Manager):**
  * Kết nối thành công tới EC2 trong Private Subnet mà không cần mở cổng inbound SSH/RDP hay quản lý Bastion Host và cặp khóa.
  * Cấu hình đầy đủ VPC Interface Endpoints (`ssm`, `ssmmessages`, `ec2messages`), S3 Gateway Endpoint để ghi nhận nhật ký phiên làm việc tập trung và thực hiện Port Forwarding.
* **Infrastructure as Code với AWS CloudFormation:**
  * Viết và triển khai CloudFormation template qua CloudShell, mở rộng khả năng xử lý bằng Custom Resources sử dụng AWS Lambda.
  * Quản lý triển khai đa vùng/đa tài khoản với Mappings và StackSets, đồng thời phát hiện thay đổi ngoài luồng bằng Drift Detection.
* **Lập trình hạ tầng với AWS CDK (Essentials & Advanced):**
  * Thành thạo quy trình phát triển CDK từ khởi tạo, `cdk synth`, `cdk diff` đến `cdk deploy` và cập nhật hạ tầng.
  * Xây dựng được các kiến trúc thực tế bằng CDK gồm ECS + ALB + API Gateway, tích hợp Lambda + S3 và tổ chức mã nguồn gọn gàng bằng Nested Stacks.
