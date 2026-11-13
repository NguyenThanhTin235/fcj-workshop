---
title: "Worklog Tuần 6"
date: 2026-10-05
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

**Thời gian:** 09/11/2026 → 13/11/2026  
**Chủ đề:** Database Migration, Serverless Automation với AWS Lambda & Monitoring với CloudWatch/Grafana  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 6:

* Thực hành chuyển đổi schema và di trú dữ liệu không đồng nhất với AWS SCT, AWS DMS (Replication Instance & DMS Serverless)
* Triển khai tự động hóa tối ưu chi phí EC2 bằng AWS Lambda (Start/Stop theo lịch) kết hợp thông báo Slack Webhook
* Cài đặt Grafana trên Linux EC2 và kết nối AWS CloudWatch để trực quan hóa metrics và thiết lập cảnh báo

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Chuẩn bị môi trường EC2 & cài đặt AWS Schema Conversion Tool (SCT)<br>- Chọn nguồn Oracle/SQL Server, chuyển đổi schema/procedural code<br>- Cấu hình target RDS/Aurora, Replication Instance và Source/Target Endpoints | 09/11/2026 | 09/11/2026 | <https://000043.awsfcaj.com/> |
| 3 | - Tạo DMS Task thực hiện Full Load và đồng bộ CDC<br>- Thử nghiệm DMS Serverless auto-scaling qua CloudWatch<br>- Giám sát metrics, event notifications, task logs, xử lý lỗi bộ nhớ/bảng và dọn dẹp tài nguyên | 10/11/2026 | 10/11/2026 | <https://000043.awsfcaj.com/> |
| 4 | - Tạo VPC, Security Group, EC2 và gắn Tag quản lý; tạo Slack Incoming Webhook<br>- Tạo IAM Role cho Lambda và viết 2 hàm Lambda tự động Start/Stop EC2<br>- Kiểm thử kết quả bật/tắt EC2 tự động, gửi thông báo Slack và dọn dẹp tài nguyên | 11/11/2026 | 11/11/2026 | <https://000022.awsfcaj.com/> |
| 5 | - Chuẩn bị hạ tầng VPC, Subnet, Security Group và EC2 Linux<br>- Tạo IAM User/Access Key và gán IAM Role cho EC2 để truy xuất CloudWatch<br>- Cài đặt và khởi chạy Grafana mã nguồn mở trên Linux EC2 | 12/11/2026 | 12/11/2026 | <https://000029.awsfcaj.com/> |
| 6 | - Kết nối Grafana với nguồn dữ liệu AWS CloudWatch<br>- Tạo dashboard trực quan hóa metrics và cấu hình cảnh báo giám sát<br>- Tổng kết tuần 6 và dọn dẹp toàn bộ tài nguyên lab | 13/11/2026 | 13/11/2026 | <https://000029.awsfcaj.com/> |

---

### Kết quả đạt được tuần 6:

* **Chuyển đổi & di trú cơ sở dữ liệu (AWS SCT & AWS DMS):**
  * Chuyển đổi thành công schema và di trú dữ liệu từ nguồn không đồng nhất sang RDS/Aurora với Full Load và CDC.
  * Nắm vững cơ chế auto-scaling của DMS Serverless, theo dõi CloudWatch metrics và xử lý sự cố trong quá trình migration.
* **Tự động hóa Serverless tối ưu chi phí với AWS Lambda:**
  * Triển khai thành công cặp hàm Lambda tự động Start/Stop các EC2 không chạy 24/7 theo Tag và gửi thông báo về Slack.
  * Phân biệt được trường hợp dùng Lambda tự động tắt/bật và Savings Plans cho workload chạy liên tục.
* **Giám sát nâng cao với CloudWatch & Grafana:**
  * Cài đặt hoàn chỉnh Grafana trên EC2 Linux và tích hợp với AWS CloudWatch qua IAM Role.
  * Xây dựng dashboard theo dõi hiệu năng và thiết lập cảnh báo tập trung cho tài nguyên AWS.
