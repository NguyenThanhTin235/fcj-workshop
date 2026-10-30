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

* Nắm vững phương thức tự động hóa và quản trị tài nguyên hạ tầng thông qua AWS Command Line Interface (AWS CLI v2)
* Tìm hiểu cơ sở dữ liệu phi quan hệ NoSQL Amazon DynamoDB: mô hình dữ liệu, phân vùng, chỉ mục và tối ưu hóa hiệu năng truy vấn
* Triển khai giải pháp bộ nhớ đệm phân tán với Amazon ElastiCache (Redis) nhằm giảm tải cơ sở dữ liệu và tăng tốc độ phản hồi ứng dụng
* Thực hành mở rộng kiến trúc mạng nâng cao với VPC Peering, AWS Transit Gateway và các giải pháp kết nối đa VPC
* Hoàn thiện chuỗi bài thực hành Networking Workshop chuyên sâu về VPC Endpoints (Gateway và Interface Endpoints) bảo vệ dữ liệu nội bộ

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu AWS CLI v2: cài đặt, cấu hình named profiles, output formats (json, yaml, text, table)<br>- Quản lý định danh an toàn: phân biệt sử dụng Access Key, AWS CloudShell và tích hợp IAM Identity Center (SSO)<br>- Thao tác tự động hóa với các dịch vụ chính: S3 (quản lý bucket/object, đồng bộ dữ liệu), EC2 (kiểm tra trạng thái, khởi tạo instance)<br>- Áp dụng kỹ thuật lọc dữ liệu đầu ra với tham số --query (JMESPath) và --filter để trích xuất thông tin chính xác | 26/10/2026 | 26/10/2026 | <https://000007.awsstudygroup.com/> |
| 3 | - Tìm hiểu nền tảng cơ sở dữ liệu NoSQL Amazon DynamoDB: mô hình Key-Value và Document<br>- Nắm vững kiến trúc Partition Key, Sort Key (Composite Primary Key) và cách phân bổ dữ liệu trên các partition<br>- Phân biệt hai chế độ quản lý năng lực (Capacity Modes): On-Demand Mode và Provisioned Mode (RCU, WCU)<br>- Thiết kế chỉ mục phụ: Local Secondary Index (LSI) và Global Secondary Index (GSI)<br>- Thực hành tạo bảng DynamoDB, thực hiện các thao tác PutItem, GetItem, so sánh hiệu năng Query vs Scan, và cấu hình Time to Live (TTL) | 27/10/2026 | 27/10/2026 | <https://000009.awsstudygroup.com/> |
| 4 | - Tìm hiểu cơ chế bộ nhớ đệm (Caching) và các chiến lược lưu cache: Cache-Aside (Lazy Loading), Write-Through và thiết lập TTL<br>- So sánh hai công cụ phổ biến trong Amazon ElastiCache: Redis (cấu trúc dữ liệu đa dạng, Multi-AZ, Read Replicas, sao lưu bền vững) vs Memcached (đa luồng, đơn giản)<br>- Triển khai cụm ElastiCache Redis Cluster trong Private Subnet của VPC, thiết lập Subnet Group và kiểm soát cổng truy cập an toàn qua Security Group<br>- Kết nối ứng dụng từ máy chủ EC2 tới ElastiCache, thực hành kỹ thuật lưu cache kết quả truy vấn nhằm hạ độ trễ xuống cấp độ mili-giây | 28/10/2026 | 28/10/2026 | <https://000011.awsstudygroup.com/> |
| 5 | - Mở rộng kiến trúc mạng đa VPC (Multi-VPC Architecture):<br>&nbsp;&nbsp;+ Thiết lập kết nối VPC Peering giữa các VPC trong cùng khu vực (Intra-Region) và khác khu vực (Inter-Region)<br>&nbsp;&nbsp;+ Cấu hình Route Table hai chiều và áp dụng kỹ thuật tham chiếu Security Group chéo VPC<br>&nbsp;&nbsp;+ Đánh giá tính chất định tuyến không bắc cầu (Non-transitive routing) của VPC Peering<br>- Tìm hiểu AWS Transit Gateway (TGW) như một hub định tuyến tập trung mô hình Hub-and-Spoke<br>- Khởi tạo Transit Gateway, gắn kết các VPC (VPC Attachments), xây dựng TGW Route Tables và kiểm tra lưu lượng kết nối thông suốt | 29/10/2026 | 29/10/2026 | <https://000012.awsstudygroup.com/> |
| 6 | - Thực hành chuyên sâu Networking Workshop về kết nối bảo mật qua AWS PrivateLink và VPC Endpoints:<br>&nbsp;&nbsp;+ Triển khai Gateway Endpoint cho Amazon S3 để truy cập dữ liệu nội bộ qua Route Table mà không cần Internet Gateway hoặc NAT Gateway<br>&nbsp;&nbsp;+ Cấu hình Interface Endpoint (AWS PrivateLink) cho phép tài nguyên on-premises và mạng riêng kết nối tới các dịch vụ AWS thông qua Private IP<br>&nbsp;&nbsp;+ Áp dụng VPC Endpoint Policies nhằm giới hạn quyền truy cập chỉ cho phép các S3 bucket và hành động được chỉ định<br>- Đánh giá tổng kết toàn bộ kiến trúc hạ tầng tuần 4: Quản trị tự động, NoSQL, In-Memory Caching và Mạng phân tán bảo mật cao<br>- Dọn dẹp tài nguyên lab (Clean up resources) | 30/10/2026 | 30/10/2026 | <https://000013.awsstudygroup.com/> |

---

### Kết quả đạt được tuần 4:

* **Tự động hóa quản trị hệ thống với AWS CLI v2:**
  * Thành thạo quy trình cài đặt, định hình nhiều hồ sơ xác thực (named profiles) và quản lý phiên đăng nhập an toàn mà không cần lưu khóa dài hạn trên môi trường phát triển.
  * Nắm vững kỹ thuật lọc dữ liệu nâng cao bằng JMESPath thông qua tham số `--query`, giúp trích xuất trực tiếp các trường thông tin cần thiết từ kết quả JSON phức tạp của AWS APIs.
  * Tự động hóa các tác vụ quản trị hàng ngày đối với S3, EC2 và IAM, nâng cao hiệu suất làm việc so với thao tác thủ công trên AWS Management Console.
* **Vận hành cơ sở dữ liệu NoSQL với Amazon DynamoDB:**
  * Hiểu sâu kiến trúc lưu trữ phân tán, cơ chế băm dữ liệu theo Partition Key và khả năng co giãn quy mô tự động không giới hạn của DynamoDB.
  * Nắm vững sự khác biệt giữa hai chế độ tính cước On-Demand và Provisioned, biết cách tính toán Read Capacity Units (RCU) và Write Capacity Units (WCU) tối ưu chi phí.
  * Phân biệt rõ sự khác nhau về mặt kiến trúc và chi phí giữa Query (tìm kiếm định hướng theo Partition Key) và Scan (quét toàn bộ bảng tốn kém tài nguyên).
  * Ứng dụng thành công Global Secondary Index (GSI) để phục vụ các mẫu truy vấn mới mà không làm thay đổi khóa chính ban đầu, đồng thời kích hoạt TTL để tự động dọn dẹp các bản ghi hết hạn.
* **Tối ưu hóa hiệu năng ứng dụng với Amazon ElastiCache:**
  * Nắm vững vai trò của tầng bộ nhớ đệm trong việc bảo vệ cơ sở dữ liệu phía sau khỏi tình trạng quá tải (thundering herd problem).
  * Lựa chọn chính xác công cụ Redis cho các bài toán đòi hỏi tính sẵn sàng cao (Multi-AZ Failover), khả năng sao lưu phục hồi dữ liệu và lưu trữ các cấu trúc dữ liệu phong phú (Hashes, Lists, Sets, Sorted Sets).
  * Triển khai cụm ElastiCache an toàn trong Private Subnet, cấu hình ứng dụng web kết nối đệm dữ liệu thành công, giúp giảm thiểu đáng kể thời gian phản hồi cho các truy vấn lặp lại.
* **Thiết kế mạng nâng cao và bảo mật kết nối nội bộ:**
  * Nắm vững các mô hình kết nối đa VPC, phân biệt rõ các kịch bản áp dụng phù hợp giữa VPC Peering (kết nối điểm - điểm với chi phí tiết kiệm) và AWS Transit Gateway (kết nối hình sao cho quy mô doanh nghiệp lớn).
  * Thực hành xuất sắc chuỗi bài lab Networking Workshop: triển khai thành công cả Gateway Endpoint và Interface Endpoint cho Amazon S3.
  * Thiết lập chặt chẽ chính sách VPC Endpoint Policy để ngăn chặn rủi ro thất thoát dữ liệu (data exfiltration), bảo đảm toàn bộ lưu lượng giao tiếp giữa máy chủ và dịch vụ lưu trữ luôn nằm trọn vẹn trong mạng cáp quang riêng của AWS.
