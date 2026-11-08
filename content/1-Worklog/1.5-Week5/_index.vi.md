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

* Triển khai mạng phân phối nội dung toàn cầu Amazon CloudFront: cấu hình phân phối đa nguồn (Multi-Origin), tối ưu hóa bộ nhớ đệm (Cache Policies, TTL) và thiết lập bảo vệ gốc an toàn với Origin Access Control (OAC)
* Nắm vững kiến trúc điện toán biên (Edge Computing): phân biệt và ứng dụng CloudFront Functions và Lambda@Edge tại 4 vị trí sự kiện (Viewer Request/Response, Origin Request/Response) để tùy biến tiêu đề, điều hướng người dùng và tối ưu bảo mật
* Gia cố phòng thủ biên ứng dụng với AWS WAF & AWS Shield: triển khai Web ACLs, cấu hình bộ quy tắc quản trị (AWS Managed Rules), Rate-based rules chống tấn công brute-force và DDoS
* Thiết kế và xây dựng ứng dụng web có tính sẵn sàng cao (High Availability): kiến trúc Multi-AZ không điểm lỗi đơn lẻ (No SPOF) kết hợp Application Load Balancer (ALB), Auto Scaling Group (ASG) và Amazon RDS Multi-AZ
* Làm chủ kỹ thuật điều phối lưu lượng toàn cầu và khôi phục sau thảm họa (Disaster Recovery): cấu hình định tuyến thông minh Route 53, tăng tốc mạng và chuyển đổi dự phòng tức thì với AWS Global Accelerator

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tổng quan mạng phân phối nội dung toàn cầu Amazon CloudFront: cấu trúc hạ tầng Edge Locations, Regional Edge Caches và cơ chế giảm độ trễ truy cập<br>- Khởi tạo CloudFront Distribution phục vụ website tĩnh và động: tích hợp Amazon S3 Origin và Custom Origin (ALB/EC2)<br>- Bảo mật truy cập gốc với Origin Access Control (OAC): thay thế OAI cũ, cấu hình S3 Bucket Policy chỉ cấp quyền cho service principal `cloudfront.amazonaws.com` với điều kiện `AWS:SourceArn`<br>- Tối ưu hóa hiệu năng bộ nhớ đệm: thiết lập Cache Policies (TTL Min/Default/Max, Cache Key), Origin Request Policies, nén dữ liệu tự động (Gzip/Brotli) và thực hành tạo lệnh xóa cache (Cache Invalidation) | 02/11/2026 | 02/11/2026 | <https://000094.awsfcaj.com/> |
| 3 | - Tìm hiểu nền tảng điện toán biên (Edge Computing) trên AWS: so sánh chuyên sâu CloudFront Functions (nhẹ, độ trễ micro-giây) vs Lambda@Edge (tính toán phức tạp, truy cập mạng/I/O)<br>- Nắm vững 4 vị trí bắt sự kiện (Event Triggers): Viewer Request, Origin Request, Origin Response, và Viewer Response<br>- Thực hành viết hàm Lambda@Edge (Node.js/Python):<br>&nbsp;&nbsp;+ Điều hướng người dùng theo vị trí địa lý dựa vào header `CloudFront-Viewer-Country`<br>&nbsp;&nbsp;+ Tự động chèn các tiêu đề bảo mật HTTP (HSTS, CSP, X-Frame-Options, X-Content-Type-Options)<br>&nbsp;&nbsp;+ Tùy biến URL Rewriting và kiểm tra xác thực mã token JWT tại biên mạng | 03/11/2026 | 03/11/2026 | <https://000130.awsfcaj.com/> |
| 4 | - Tăng cường bảo mật biên ứng dụng với AWS WAF (Web Application Firewall):<br>&nbsp;&nbsp;+ Giới thiệu kiến trúc tường lửa ứng dụng web, mô hình kiểm soát Layer 7 cho CloudFront và ALB<br>&nbsp;&nbsp;+ Khởi tạo Web ACL và liên kết trực tiếp với CloudFront Distribution<br>&nbsp;&nbsp;+ Thiết lập các bộ quy tắc AWS Managed Rules (Core Rule Set - CRS, SQLi, XSS) và IP Reputation Lists<br>&nbsp;&nbsp;+ Xây dựng Custom Rules: quy tắc giới hạn tần suất (Rate-based rules) ngăn chặn brute-force và lọc truy cập theo địa lý (Geo-blocking)<br>&nbsp;&nbsp;+ Vận hành thử nghiệm với chế độ Count trước khi chuyển sang Block, cấu hình phân tích nhật ký (Request Logging) lưu trữ trên S3 | 04/11/2026 | 04/11/2026 | <https://000026.awsfcaj.com/> |
| 5 | - Xây dựng ứng dụng Web có tính sẵn sàng cao (Building Highly Available Web Applications):<br>&nbsp;&nbsp;+ Hoạch định kiến trúc chịu lỗi (Fault-Tolerant), triệt tiêu các điểm lỗi đơn lẻ (Single Points of Failure - SPOF)<br>&nbsp;&nbsp;+ Triển khai hạ tầng mạng Multi-AZ trên Amazon VPC: chia tách Public Subnet (ALB) và Private Subnet (Web Server, Database)<br>&nbsp;&nbsp;+ Cấu hình Application Load Balancer (ALB) kèm cơ chế Health Checks điều hướng lưu lượng tự động đến các máy chủ khỏe mạnh<br>&nbsp;&nbsp;+ Thiết lập Auto Scaling Group (ASG) trải rộng đa AZ: cấu hình Launch Template, chính sách co giãn động (Dynamic Scaling - Target Tracking CPU) và cơ chế tự phục hồi (Self-healing)<br>&nbsp;&nbsp;+ Triển khai cơ sở dữ liệu quan hệ Amazon RDS Multi-AZ với tính năng tự động sao chép đồng bộ và tự chuyển đổi dự phòng (Automated Failover) | 05/11/2026 | 05/11/2026 | <https://000101.awsfcaj.com/> |
| 6 | - Quản trị lưu lượng toàn cầu và khôi phục sau thảm họa (Disaster Recovery & Global Traffic Management):<br>&nbsp;&nbsp;+ Tìm hiểu các chính sách định tuyến thông minh với Amazon Route 53: Latency-based Routing, Geolocation Routing và Failover Routing dựa trên Route 53 Health Checks<br>&nbsp;&nbsp;+ Triển khai AWS Global Accelerator: sử dụng 2 địa chỉ Anycast Static IP tĩnh đưa traffic vào mạng cáp quang nội bộ AWS, rút ngắn độ trễ và chuyển đổi dự phòng tức thì giữa các vùng (Regions)<br>&nbsp;&nbsp;+ So sánh và lựa chọn chiến lược Disaster Recovery: Backup & Restore, Pilot Light, Warm Standby và Multi-Region Active/Active dựa trên mục tiêu RTO và RPO<br>- Đánh giá tổng kết tuần 5: Toàn diện giải pháp tăng tốc phân phối nội dung, điện toán biên, bảo vệ tầng ứng dụng và kiến trúc sẵn sàng cao<br>- Dọn dẹp tài nguyên lab (Clean up resources) | 06/11/2026 | 06/11/2026 | <https://000101.awsfcaj.com/> |

---

### Kết quả đạt được tuần 5:

* **Tăng tốc phân phối nội dung và tối ưu bảo mật gốc với Amazon CloudFront:**
  * Hiểu sâu nguyên lý hoạt động của hệ thống mạng phân phối nội dung biên (CDN), cơ chế giảm thiểu tải cho máy chủ gốc và tiết kiệm chi phí băng thông mạng.
  * Triển khai thành công CloudFront Distribution tích hợp S3 và Custom Origins, làm chủ việc cấu hình Cache Policy, Origin Request Policy và tính năng nén Gzip/Brotli.
  * Áp dụng thành công cơ chế Origin Access Control (OAC) mới nhất với chuẩn ký SigV4, khóa chặt quyền truy cập S3 Bucket chỉ qua CloudFront, ngăn chặn việc truy cập trực tiếp từ Internet.
* **Tùy biến xử lý dữ liệu tại biên với Edge Computing (Lambda@Edge & CloudFront Functions):**
  * Nắm vững kiến trúc và ranh giới áp dụng giữa CloudFront Functions (xử lý nhẹ, tốc độ cao) và Lambda@Edge (xử lý tính toán chuyên sâu, tương tác mạng).
  * Vận dụng thành thạo 4 điểm bắt sự kiện (Viewer Request/Response, Origin Request/Response) để can thiệp luồng dữ liệu trước khi đến máy chủ gốc hoặc người dùng.
  * Triển khai thành công mã nguồn Lambda@Edge xử lý định tuyến thông minh theo quốc gia (Geo-redirection) và tự động gắn các tiêu đề bảo mật HTTP (Security Headers) bảo vệ trình duyệt người dùng.
* **Bảo vệ ứng dụng web toàn diện với AWS WAF:**
  * Xây dựng lá chắn bảo mật Layer 7 vững chắc tại biên mạng, giảm tải cho các tầng máy chủ ứng dụng bên trong VPC.
  * Tận dụng hiệu quả AWS Managed Rules để ngăn ngừa các lỗ hổng bảo mật phổ biến thuộc OWASP Top 10 mà không cần viết mã thủ công.
  * Xây dựng các Custom Rules ngăn chặn tấn công từ chối dịch vụ (Rate-based rules) và rà soát lưu lượng nghi vấn an toàn thông qua quy trình thử nghiệm chế độ Count trước khi kích hoạt Block.
* **Xây dựng hệ thống web có tính sẵn sàng cao (High Availability):**
  * Thiết kế hoàn chỉnh kiến trúc web 3 tầng (Web/App/DB) chuẩn chỉnh trên mô hình Multi-AZ, loại bỏ hoàn toàn các điểm lỗi đơn lẻ (SPOF).
  * Làm chủ cơ chế cân bằng tải thông minh với Application Load Balancer và hệ thống tự động co giãn / tự phục hồi của Auto Scaling Group khi có máy chủ gặp sự cố.
  * Thiết lập cơ chế cơ sở dữ liệu quan hệ Amazon RDS Multi-AZ có tính sẵn sàng cao, đảm bảo hoạt động liên tục (High Availability) và không bị gián đoạn dịch vụ khi xảy ra sự cố tại một Availability Zone.
* **Điều phối mạng toàn cầu và sẵn sàng khôi phục sau thảm họa:**
  * Phân biệt rõ sự khác nhau về cơ chế định tuyến và độ trễ failover giữa DNS Route 53 (phụ thuộc TTL) và AWS Global Accelerator (chuyển hướng Anycast IP trong vài giây).
  * Nắm vững các mô hình Disaster Recovery từ cơ bản đến nâng cao (Backup/Restore, Pilot Light, Warm Standby, Active/Active), hiểu rõ cách tính toán chi phí và đáp ứng chỉ số RTO/RPO cho doanh nghiệp.

