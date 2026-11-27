---
title: "Worklog Tuần 8"
date: 2026-10-05
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

**Thời gian:** 23/11/2026 → 27/11/2026  
**Chủ đề:** Infrastructure as Code (Three-Tier CloudFormation), EC2 Right-Sizing, VPC Flow Logs, Quản trị chi phí với IAM & Tự động hóa/Phát hiện bất thường EBS Backup  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 8:

* Triển khai kiến trúc Web 3 tầng (Web, Application, Database tiers) cùng Lambda, VPC và EC2 bằng AWS CloudFormation
* Tối ưu hóa chi phí compute thông qua việc thu thập metrics bằng Amazon CloudWatch Agent và phân tích khuyến nghị trong Cost Optimization Hub và AWS Compute Optimizer
* Giám sát lưu lượng mạng và phân tích kết nối bằng cách kích hoạt và theo dõi Amazon VPC Flow Logs
* Thực thi quản trị chi phí và tài nguyên bằng các IAM Policy giới hạn Region, dòng/kích thước EC2 instance và EBS volume
* Tự động hóa lưu trữ snapshot EBS với Amazon Data Lifecycle Manager (DLM) và phát hiện bất thường sao lưu bằng AWS Backup anomaly detection

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Chuẩn bị môi trường và triển khai Lambda, VPC, EC2 bằng AWS CloudFormation<br>- Triển khai CloudFormation Stack cho kiến trúc Three-Tier và kiểm thử truy cập tầng Web, Application, Database<br>- Dọn dẹp các CloudFormation stack và tài nguyên lab | 23/11/2026 | 23/11/2026 | <https://000102.awsfcaj.com/> |
| 3 | - Khởi chạy EC2 instance, tạo và gắn IAM Role cho CloudWatch Agent, cài đặt CloudWatch Agent<br>- Xem xét các khuyến nghị right-sizing EC2 trên Cost Optimization Hub và AWS Compute Optimizer<br>- Áp dụng best practices về right-sizing cho Amazon EC2 và dọn dẹp tài nguyên | 24/11/2026 | 24/11/2026 | <https://000032.awsfcaj.com/> |
| 4 | - Chuẩn bị hạ tầng mạng, tạo và kích hoạt Amazon VPC Flow Logs<br>- Giám sát hạ tầng mạng và phân tích dữ liệu flow logs<br>- Dọn dẹp VPC Flow Logs và tài nguyên lab | 25/11/2026 | 25/11/2026 | <https://000074.awsfcaj.com/> |
| 5 | - Tạo IAM Group và IAM User phục vụ kiểm thử quản trị chi phí<br>- Tạo, gắn và kiểm thử hiệu lực các IAM Policy giới hạn Region, EC2 instance family, kích thước EC2 và EBS volume<br>- Dọn dẹp IAM user, group và policy | 26/11/2026 | 26/11/2026 | <https://000064.awsfcaj.com/> |
| 6 | - Khởi chạy EC2, cấu hình Single và Multiple Policy Schedule trên Amazon DLM để tự động lưu trữ (archive) EBS Snapshots và kiểm tra kết quả<br>- Tạo S3 bucket, EBS volume và CloudFormation stack để thực hành AWS Backup anomaly detection và theo dõi cảnh báo<br>- Tổng kết tuần 8 và dọn dẹp toàn bộ tài nguyên lab | 27/11/2026 | 27/11/2026 | <https://000088.awsfcaj.com/><br><https://000089.awsfcaj.com/> |

---

### Kết quả đạt được tuần 8:

* **Infrastructure as Code (Three-Tier CloudFormation):**
  * Triển khai hoàn chỉnh kiến trúc 3 tầng (Web, Application, Database) cùng VPC, EC2 và Lambda bằng AWS CloudFormation, kiểm chứng kết nối thông suốt giữa các tầng.
* **EC2 Right-Sizing & Quản trị chi phí với IAM:**
  * Cài đặt CloudWatch Agent thu thập metrics chi tiết cấp hệ điều hành để nhận khuyến nghị right-sizing chính xác từ Cost Optimization Hub và AWS Compute Optimizer.
  * Áp dụng kiểm soát phòng ngừa chi phí bằng IAM Policy giới hạn Region, dòng máy/kích thước EC2 và dung lượng/loại EBS volume được phép khởi tạo.
* **Giám sát mạng & An toàn sao lưu EBS:**
  * Kích hoạt VPC Flow Logs để ghi nhận và giám sát lưu lượng IP ra/vào các giao diện mạng trong VPC.
  * Tự động hóa vòng đời lưu trữ snapshot EBS qua lịch trình Amazon DLM và thiết lập AWS Backup anomaly detection nhằm phát hiện sớm các bất thường trong quá trình sao lưu EBS.
