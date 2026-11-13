---
title: "Worklog Tuần 3"
date: 2026-10-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Thời gian:** 19/10/2026 → 23/10/2026  
**Chủ đề:** Amazon RDS, Amazon Lightsail & Containers, EC2 Auto Scaling, Amazon CloudWatch & Route 53  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 3:

* Quản trị Amazon RDS: Multi-AZ, Read Replicas và sao lưu phục hồi
* Triển khai WordPress VPS và Container Service trên Amazon Lightsail
* Xây dựng hệ thống cân bằng tải và tự động co giãn với ALB & Auto Scaling Group (ASG)
* Giám sát tập trung với Amazon CloudWatch (Metrics, Agent, Logs Insights, Alarms, Dashboards)
* Triển khai Hybrid DNS hai chiều với Amazon Route 53 Resolver

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu RDS Multi-AZ đồng bộ, Read Replicas bất đồng bộ, lưu trữ gp3 SSD<br>- Triển khai RDS MySQL trong Private Subnet (DB Subnet Group đa AZ), mở cổng 3306 từ EC2, kiểm tra CRUD và tạo DB Snapshot | 19/10/2026 | 19/10/2026 | <https://000005.awsstudygroup.com/> |
| 3 | - Triển khai WordPress trên Lightsail VPS, gắn Static IP, cài SSL Let's Encrypt và tách sang Lightsail Managed Database<br>- Cài `lightsailctl` & Docker CLI, đóng gói ứng dụng đẩy lên Lightsail Container Service và cấu hình Health check | 20/10/2026 | 20/10/2026 | <https://000045.awsstudygroup.com/><br><https://000046.awsstudygroup.com/> |
| 4 | - Tạo Launch Template (AMI + User Data), Application Load Balancer (ALB) và Target Group<br>- Cấu hình Auto Scaling Group đa AZ (Min/Desired/Max) và kiểm thử Manual, Scheduled, Dynamic Scaling (CPU > 50%) | 21/10/2026 | 21/10/2026 | <https://000006.awsstudygroup.com/> |
| 5 | - Theo dõi CloudWatch Metrics (Metric Math, Search Expressions) và cài CloudWatch Unified Agent thu thập RAM/Disk/Log<br>- Truy vấn với CloudWatch Logs Insights, tạo Alarms gửi qua Amazon SNS và dựng Dashboard | 22/10/2026 | 22/10/2026 | <https://000008.awsstudygroup.com/> |
| 6 | - Giả lập On-premises AD Domain Controller qua CloudFormation<br>- Cấu hình Route 53 Inbound/Outbound Endpoints & Resolver Rules, kiểm thử phân giải DNS hai chiều và dọn dẹp lab | 23/10/2026 | 23/10/2026 | <https://000010.awsstudygroup.com/> |

---

### Kết quả đạt được tuần 3:

* **Amazon RDS:** Triển khai RDS MySQL bảo mật trong Private Subnet, nắm vững cơ chế failover Multi-AZ, Read Replicas và Point-in-time recovery.
* **Amazon Lightsail:** Vận hành WordPress VPS (Static IP, SSL, Managed Database) và triển khai container qua `lightsailctl` trên Lightsail Container Service.
* **ALB & Auto Scaling:** Chuẩn hóa máy chủ bằng Launch Template, phân phối tải qua ALB và kiểm thử co giãn tự động theo tải CPU.
* **Amazon CloudWatch:** Thu thập metrics RAM/Disk qua CloudWatch Agent, phân tích log bằng Logs Insights và cảnh báo tự động qua SNS.
* **Amazon Route 53:** Triển khai thành công Hybrid DNS hai chiều giữa On-premises và AWS Private Hosted Zones qua Inbound/Outbound Endpoints.
