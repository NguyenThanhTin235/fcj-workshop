---
title: "Worklog Tuần 3"
date: 2026-10-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Thời gian:** 19/10/2026 → 23/10/2026  
**Chủ đề:** Amazon RDS, Amazon Lightsail & Containers, EC2 Auto Scaling, Amazon CloudWatch & Route 53  
**Trạng thái:** Hoàn thành

### Mục tiêu tuần 3:

* Quản trị cơ sở dữ liệu quan hệ Amazon RDS: kiến trúc Multi-AZ, Read Replicas và sao lưu phục hồi
* Khám phá nền tảng Amazon Lightsail: triển khai WordPress VPS và vận hành Container Service
* Thiết lập hệ thống co giãn tự động và cân bằng tải với Application Load Balancer (ALB) và Auto Scaling Group (ASG)
* Giám sát hệ thống toàn diện với Amazon CloudWatch: Metrics, Logs Insights, Alarms và Dashboards
* Triển khai kiến trúc DNS phân giải lai (Hybrid DNS) với Amazon Route 53 Resolver

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu Amazon RDS: Multi-AZ (đồng bộ), Read Replicas (bất đồng bộ), lưu trữ gp3 SSD<br>- Triển khai RDS MySQL trong Private Subnet, cấu hình DB Subnet Group đa AZ<br>- Cấu hình Security Group mở cổng 3306 chỉ cho phép kết nối từ EC2 Web Server<br>- Kết nối ứng dụng kiểm tra thao tác CRUD và thiết lập sao lưu tự động / tạo DB Snapshot | 19/10/2026 | 19/10/2026 | <https://000005.awsstudygroup.com/> |
| 3 | - Triển khai VPS WordPress trên Amazon Lightsail, gắn Static IP và cài đặt SSL Let's Encrypt<br>- Di chuyển cơ sở dữ liệu sang Amazon Lightsail Managed Database<br>- Cài đặt plugin `lightsailctl`, Docker CLI và triển khai Public Container Image<br>- Đóng gói ứng dụng web cục bộ thành Docker image, đẩy lên Lightsail Container Service và cấu hình Health check | 20/10/2026 | 20/10/2026 | <https://000045.awsstudygroup.com/><br><https://000046.awsstudygroup.com/> |
| 4 | - Tạo Launch Template chuẩn hóa với AMI và User Data script tự động cấu hình Web Server<br>- Khởi tạo Application Load Balancer (ALB) và Target Group kèm kiểm tra sức khỏe (Health Check)<br>- Cấu hình Auto Scaling Group (ASG) đa AZ với các thông số Min, Desired, Max Capacity<br>- Kiểm thử các chính sách mở rộng: Manual Scaling, Scheduled Scaling và Dynamic Scaling (Target Tracking CPU > 50%) | 21/10/2026 | 21/10/2026 | <https://000006.awsstudygroup.com/> |
| 5 | - Theo dõi chỉ số EC2/RDS trên CloudWatch Metrics, áp dụng Metric Math và Search Expressions<br>- Cài đặt CloudWatch Unified Agent trên EC2 để thu thập Memory/Disk và file log hệ điều hành<br>- Phân tích nhật ký tập trung với CloudWatch Logs Insights bằng câu lệnh truy vấn thống kê<br>- Thiết lập CloudWatch Alarms gửi email cảnh báo qua Amazon SNS và dựng CloudWatch Dashboard tổng hợp | 22/10/2026 | 22/10/2026 | <https://000008.awsstudygroup.com/> |
| 6 | - Tìm hiểu kiến trúc Hybrid DNS với Route 53 Resolver: Inbound/Outbound Endpoints và Resolver Rules<br>- Khởi tạo môi trường giả lập On-premises với Active Directory Domain Controller qua CloudFormation<br>- Cấu hình Route 53 Outbound Endpoint & Resolver Rule chuyển tiếp truy vấn miền on-prem<br>- Cấu hình Route 53 Inbound Endpoint cho phép on-prem phân giải Private Hosted Zone trên AWS<br>- Kiểm tra phân giải DNS hai chiều thành công và dọn dẹp tài nguyên lab | 23/10/2026 | 23/10/2026 | <https://000010.awsstudygroup.com/> |

---

### Kết quả đạt được tuần 3:

* **Quản trị cơ sở dữ liệu với Amazon RDS:**
  * Phân biệt rõ mô hình tự vận hành DB trên EC2 và dịch vụ quản trị toàn diện Amazon RDS.
  * Nắm vững cơ chế chuyển đổi dự phòng tự động của kiến trúc Multi-AZ và khả năng mở rộng đọc của Read Replicas.
  * Triển khai thành công RDS MySQL trong Private Subnet, kết nối bảo mật với EC2 qua cổng 3306 và thiết lập Point-in-time recovery.
* **Điện toán đơn giản hóa với Amazon Lightsail:**
  * Nắm vững mô hình chi phí cố định của Lightsail VPS, triển khai thành công WordPress có gắn Static IP và chứng chỉ SSL.
  * Tách cơ sở dữ liệu sang Lightsail Managed Database nâng cao tính sẵn sàng.
  * Thành thạo công cụ `lightsailctl`, đóng gói và triển khai container trên Lightsail Container Service kèm cấu hình Health check.
* **Co giãn tự động & Cân bằng tải với EC2 Auto Scaling:**
  * Hiểu sâu nguyên lý co giãn đàn hồi (Elasticity) và phân phối tải lưu lượng với Application Load Balancer (ALB).
  * Chuẩn hóa môi trường máy chủ thông qua Launch Template và Target Group Health Checks.
  * Vận hành Auto Scaling Group đa AZ, kiểm thử thành công chính sách co giãn tự động theo tải CPU thực tế.
* **Giám sát tập trung với Amazon CloudWatch:**
  * Thu thập số liệu chuyên sâu về RAM và Disk bằng CloudWatch Agent trên máy chủ EC2.
  * Truy vấn và lọc log nhanh chóng thông qua CloudWatch Logs Insights.
  * Tự động hóa cảnh báo qua email với CloudWatch Alarms & Amazon SNS, trực quan hóa hạ tầng trên CloudWatch Dashboard.
* **Hạ tầng phân giải tên miền lai với Amazon Route 53:**
  * Hiểu rõ kiến trúc kết nối DNS giữa On-premises và AWS Private Hosted Zones.
  * Cấu hình hoàn chỉnh Route 53 Inbound & Outbound Endpoints kết hợp Resolver Rules.
  * Kiểm thử thành công tính năng phân giải DNS hai chiều thông suốt và dọn dẹp an toàn toàn bộ tài nguyên lab.
