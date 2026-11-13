---
title: "Worklog Tuần 5"
date: 2026-10-05
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Thời gian:** 02/11/2026 → 06/11/2026  
**Chủ đề:** CloudFront, Edge Computing & High Availability  
**Trạng thái:** Đã hoàn thành

### Mục tiêu tuần 5:

* Triển khai Amazon CloudFront đa nguồn (S3, ALB/EC2), tối ưu Cache Policies và bảo vệ gốc bằng OAC
* Ứng dụng Edge Computing (CloudFront Functions & Lambda@Edge) tại 4 sự kiện biên
* Bảo vệ lớp ứng dụng với AWS WAF (Web ACLs, Managed Rules, Rate-based rules) & AWS Shield
* Thiết kế ứng dụng web High Availability Multi-AZ (ALB, ASG, RDS Multi-AZ) và điều phối lưu lượng toàn cầu (Route 53, Global Accelerator, DR)

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu CloudFront (Edge Locations, Regional Edge Caches); tạo Distribution với S3 & Custom Origin<br>- Cấu hình Origin Access Control (OAC) khóa S3 Bucket Policy (`AWS:SourceArn`), tối ưu Cache/Origin Request Policies, nén Gzip/Brotli và Cache Invalidation | 02/11/2026 | 02/11/2026 | <https://000094.awsfcaj.com/> |
| 3 | - So sánh CloudFront Functions vs Lambda@Edge và 4 Event Triggers (Viewer/Origin Request & Response)<br>- Viết Lambda@Edge điều hướng theo `CloudFront-Viewer-Country`, chèn HTTP security headers (HSTS, CSP, X-Frame-Options), URL Rewriting và kiểm tra JWT | 03/11/2026 | 03/11/2026 | <https://000130.awsfcaj.com/> |
| 4 | - Tạo AWS WAF Web ACL gắn với CloudFront: cấu hình AWS Managed Rules (CRS, SQLi, XSS, IP Reputation) và Custom Rules (Rate-based, Geo)<br>- Thử nghiệm chế độ Count trước khi chuyển Block và lưu log phân tích trên S3 | 04/11/2026 | 04/11/2026 | <https://000026.awsfcaj.com/> |
| 5 | - Xây dựng kiến trúc Multi-AZ không SPOF: Public/Private Subnets, ALB với Health Checks, Auto Scaling Group (Launch Template, Target Tracking CPU) và RDS Multi-AZ | 05/11/2026 | 05/11/2026 | <https://000101.awsfcaj.com/> |
| 6 | - Cấu hình Route 53 (Latency/Geolocation/Failover Routing) và AWS Global Accelerator (2 Anycast Static IP)<br>- So sánh chiến lược Disaster Recovery (Backup & Restore, Pilot Light, Warm Standby, Multi-Region Active/Active theo RTO/RPO), tổng kết tuần 5 và dọn dẹp lab | 06/11/2026 | 06/11/2026 | <https://000101.awsfcaj.com/> |

---

### Kết quả đạt được tuần 5:

* **Amazon CloudFront & OAC:** Triển khai CDN đa nguồn, tối ưu Cache Policies, nén Gzip/Brotli và khóa chặt quyền truy cập S3 qua OAC (SigV4).
* **Edge Computing:** Phân biệt rõ CloudFront Functions và Lambda@Edge; triển khai hàm xử lý định tuyến quốc gia và gắn security headers tại biên.
* **AWS WAF:** Bảo vệ Layer 7 bằng AWS Managed Rules chống OWASP Top 10, kết hợp Custom Rate-based rules và kiểm thử an toàn qua chế độ Count.
* **High Availability & DR:** Hoàn thiện kiến trúc web 3 tầng Multi-AZ (ALB + ASG + RDS Multi-AZ), phân biệt Route 53 vs Global Accelerator và nắm vững các mô hình DR theo RTO/RPO.
