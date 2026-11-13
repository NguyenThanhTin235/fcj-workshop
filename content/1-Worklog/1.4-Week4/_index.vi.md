---
title: "Worklog Tuần 4"
date: 2026-10-05
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

**Thời gian:** 26/10/2026 → 30/10/2026  
**Chủ đề:** AWS CLI, Amazon DynamoDB, Amazon ElastiCache & Networking Workshop  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 4:

* Tự động hóa quản trị S3, SNS, IAM, VPC và EC2 bằng AWS CLI v2
* Vận hành NoSQL Amazon DynamoDB (On-Demand/Provisioned, GSI/LSI) và lập trình CRUD với Python (`boto3`)
* Triển khai bộ nhớ đệm Amazon ElastiCache (Redis) ở hai chế độ Cluster Mode Disabled/Enabled
* Hoàn thiện Networking Workshop: quy hoạch RFC 1918 đa VPC, VPC Peering, Transit Gateway và VPC Endpoints

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Cài đặt AWS CLI v2, cấu hình named profiles, output formats và `--cli-auto-prompt`<br>- Thực hành CLI với S3 (`mb`, `cp`, `sync`, `rb`), SNS (Topic/Subscription/Publish), IAM (Group/User/Access Keys), tạo trọn gói VPC/EC2 và lọc dữ liệu bằng `--query` (JMESPath) / `--filter` | 26/10/2026 | 26/10/2026 | <https://000011.awsfcaj.com/> |
| 3 | - Tìm hiểu DynamoDB (Tables/Items/Attributes, On-Demand vs Provisioned RCU/WCU, Eventually vs Strongly Consistent Reads, LSI/GSI, Query vs Scan)<br>- Tạo bảng, thực hiện PutItem/GetItem/UpdateItem/DeleteItem và viết script Python `boto3` | 27/10/2026 | 27/10/2026 | <https://000060.awsfcaj.com/> |
| 4 | - Tìm hiểu ElastiCache Redis: Cluster Mode Disabled (Primary + Replicas) vs Enabled (Shards), các loại Endpoint (Primary/Reader/Configuration/Node)<br>- Triển khai cụm Redis trong Private Subnet, kiểm thử từ EC2 qua `redis-cli` (SET, GET, TTL) và Python `redis-py` | 28/10/2026 | 28/10/2026 | <https://000061.awsfcaj.com/> |
| 5 | - Networking Workshop (Phần 1): quy hoạch dải RFC 1918 (`10.0.0.0/8`) cho đa VPC (Non-Prod, Prod, Shared Services, Datacenter)<br>- Cấu hình Subnets, Route Tables, IGW, NAT Gateway, Security Groups, Network ACLs và kết nối liên VPC qua VPC Peering | 29/10/2026 | 29/10/2026 | <https://000092.awsfcaj.com/> |
| 6 | - Networking Workshop (Phần 2): triển khai AWS Transit Gateway (Hub-and-Spoke), Gateway Endpoint cho S3 và Interface Endpoint (PrivateLink) kèm VPC Endpoint Policies<br>- Tổng kết tuần 4 và dọn dẹp toàn bộ tài nguyên lab | 30/10/2026 | 30/10/2026 | <https://000092.awsfcaj.com/> |

---

### Kết quả đạt được tuần 4:

* **AWS CLI v2:** Làm chủ named profiles, `--cli-auto-prompt`, JMESPath `--query` và khởi tạo trọn gói S3, SNS, IAM, VPC, EC2 qua dòng lệnh.
* **Amazon DynamoDB:** Thiết kế thành công bảng, GSI/LSI, tối ưu Query thay Scan, phân biệt Read Consistency và tự động hóa CRUD bằng Python `boto3`.
* **Amazon ElastiCache (Redis):** Triển khai cụm Redis trong Private Subnet, phân biệt Cluster Mode Disabled/Enabled và kiểm thử cache mili-giây qua `redis-cli` và `redis-py`.
* **Networking Workshop:** Quy hoạch thành thạo hạ tầng đa VPC chuẩn RFC 1918, kết nối liên VPC bằng VPC Peering & Transit Gateway và bảo mật lưu lượng nội bộ qua Gateway/Interface VPC Endpoints.
