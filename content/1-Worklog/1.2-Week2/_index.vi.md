---
title: "Worklog Tuần 2"
date: 2026-10-05
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

**Thời gian:** 12/10/2026 → 16/10/2026  
**Chủ đề:** EC2, IAM Roles, S3 & RDS  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 2:

* Khởi tạo, kết nối an toàn và triển khai ứng dụng web trên Amazon EC2
* Gán IAM Role cho EC2 truy cập dịch vụ AWS không cần hardcode Access Key
* Lưu trữ đối tượng và host website tĩnh trên Amazon S3
* Triển khai Amazon RDS trong Private Subnet và kết nối từ ứng dụng trên EC2

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu Amazon EC2 (Instance types, AMI, EBS Volumes, các họ máy chủ)<br>- Khởi tạo EC2 Amazon Linux 2023 trong Public Subnet, tạo Key Pair (`.pem`) và Security Group (cổng 22 SSH, 80 HTTP) | 12/10/2026 | 12/10/2026 | <https://000004.awsstudygroup.com/> |
| 3 | - Kết nối EC2 qua SSH Client & EC2 Instance Connect; quản lý EBS Volume, Snapshot và tạo Custom AMI<br>- Cài đặt LAMP/Node.js, triển khai ứng dụng AWS User Management và truy cập qua Public IPv4/Elastic IP | 13/10/2026 | 13/10/2026 | <https://000004.awsstudygroup.com/> |
| 4 | - Tìm hiểu rủi ro hardcode Access Key, cơ chế IAM Instance Profile & IMDSv2<br>- Tạo S3 Bucket, IAM Role (`AmazonS3ReadOnlyAccess`), gán vào EC2 và kiểm tra truy vấn S3 qua AWS CLI | 14/10/2026 | 14/10/2026 | <https://000048.awsstudygroup.com/> |
| 5 | - Tìm hiểu Amazon S3 (Bucket, Object, S3 URI, độ bền 11 số 9, Versioning, Lifecycle)<br>- Bật Static Website Hosting, tải mã nguồn HTML/CSS/JS, cấu hình Bucket Policy Public Read và kiểm tra Website Endpoint | 15/10/2026 | 15/10/2026 | <https://000057.awsstudygroup.com/> |
| 6 | - Tìm hiểu Amazon RDS (MySQL/PostgreSQL/MariaDB, Multi-AZ, Read Replicas)<br>- Tạo DB Subnet Group (Private Subnets), khởi tạo RDS MySQL, mở cổng 3306 cho EC2, kiểm tra CRUD và dọn dẹp tài nguyên | 16/10/2026 | 16/10/2026 | <https://000005.awsstudygroup.com/> |

---

### Kết quả đạt được tuần 2:

* **Amazon EC2:** Khởi tạo thành công EC2 Amazon Linux 2023, kết nối qua SSH/Instance Connect, quản lý EBS Volume/Snapshot/Custom AMI và chạy ứng dụng AWS User Management qua Elastic IP.
* **IAM Roles cho EC2:** Gán IAM Role (`AmazonS3ReadOnlyAccess`) qua Instance Profile, truy vấn S3 bằng AWS CLI mà không lưu Access Key trên máy chủ.
* **Amazon S3:** Nắm vững Versioning, Lifecycle Rules và triển khai thành công Static Website Hosting với Bucket Policy công khai.
* **Amazon RDS:** Triển khai RDS MySQL trong Private Subnet (DB Subnet Group), kết nối bảo mật cổng 3306 từ EC2, kiểm tra CRUD và dọn dẹp tài nguyên.
