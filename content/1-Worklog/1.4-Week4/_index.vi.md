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
* Hoàn thiện chuỗi bài thực hành Networking Workshop chuyên sâu: kết nối Amazon S3 an toàn từ VPC và On-premises qua Gateway Endpoint và Interface Endpoint

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu AWS CLI v2: cài đặt, cấu hình named profiles, output formats (json, yaml, text, table)<br>- Quản lý định danh an toàn: phân biệt sử dụng Access Key, AWS CloudShell và tích hợp IAM Identity Center (SSO)<br>- Thao tác tự động hóa với các dịch vụ chính: S3 (quản lý bucket/object, đồng bộ dữ liệu), EC2 (kiểm tra trạng thái, khởi tạo instance)<br>- Áp dụng kỹ thuật lọc dữ liệu đầu ra với tham số --query (JMESPath) và --filter để trích xuất thông tin chính xác | 26/10/2026 | 26/10/2026 | <https://000011.awsstudygroup.com/> |
| 3 | - Tìm hiểu nền tảng cơ sở dữ liệu NoSQL Amazon DynamoDB: mô hình Key-Value và Document<br>- Nắm vững kiến trúc Partition Key, Sort Key (Composite Primary Key) và cách phân bổ dữ liệu trên các partition<br>- Phân biệt hai chế độ quản lý năng lực (Capacity Modes): On-Demand Mode và Provisioned Mode (RCU, WCU)<br>- Thiết kế chỉ mục phụ: Local Secondary Index (LSI) và Global Secondary Index (GSI)<br>- Thực hành tạo bảng DynamoDB, thực hiện các thao tác PutItem, GetItem, so sánh hiệu năng Query vs Scan, và cấu hình Time to Live (TTL) | 27/10/2026 | 27/10/2026 | <https://000060.awsstudygroup.com/> |
| 4 | - Tìm hiểu cơ chế bộ nhớ đệm (Caching) và các chiến lược lưu cache: Cache-Aside (Lazy Loading), Write-Through và thiết lập TTL<br>- So sánh hai công cụ phổ biến trong Amazon ElastiCache: Redis (cấu trúc dữ liệu đa dạng, Multi-AZ, Read Replicas, sao lưu bền vững) vs Memcached (đa luồng, đơn giản)<br>- Triển khai cụm ElastiCache Redis Cluster trong Private Subnet của VPC, thiết lập Subnet Group và kiểm soát cổng truy cập an toàn qua Security Group<br>- Kết nối ứng dụng từ máy chủ EC2 tới ElastiCache, thực hành kỹ thuật lưu cache kết quả truy vấn nhằm hạ độ trễ xuống cấp độ mili-giây | 28/10/2026 | 28/10/2026 | <https://000061.awsstudygroup.com/> |
| 5 | - Networking Workshop (Phần 1):<br>&nbsp;&nbsp;+ Tìm hiểu kiến trúc kết nối riêng tư với dịch vụ AWS qua VPC Endpoints (AWS PrivateLink)<br>&nbsp;&nbsp;+ Chuẩn bị tài nguyên hạ tầng cơ sở: VPC, Public/Private Subnets, EC2 Instances và S3 Buckets<br>&nbsp;&nbsp;+ Khởi tạo Gateway Endpoint cho Amazon S3 gắn vào Route Table của Private Subnet<br>&nbsp;&nbsp;+ Kiểm tra truy cập S3 từ máy chủ EC2 nội bộ mà không cần kết nối qua Internet Gateway hay NAT Gateway | 29/10/2026 | 29/10/2026 | <https://000092.awsstudygroup.com/> |
| 6 | - Networking Workshop (Phần 2) & Tổng kết:<br>&nbsp;&nbsp;+ Khởi tạo Interface Endpoint cho Amazon S3 với Elastic Network Interface (ENI) và địa chỉ IP riêng<br>&nbsp;&nbsp;+ Mô phỏng môi trường On-premises kết nối tới S3 thông qua Interface Endpoint và DNS Resolution<br>&nbsp;&nbsp;+ Cấu hình chính sách VPC Endpoint Policies nhằm giới hạn chặt chẽ quyền truy cập bucket<br>- Đánh giá tổng kết tuần 4: Quản trị tự động với CLI, cơ sở dữ liệu NoSQL DynamoDB, bộ nhớ đệm ElastiCache và kiến trúc bảo mật với VPC Endpoints<br>- Dọn dẹp tài nguyên lab (Clean up resources) | 30/10/2026 | 30/10/2026 | <https://000092.awsstudygroup.com/> |

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
* **Bảo mật kết nối mạng chuyên sâu với Networking Workshop:**
  * Hiểu sâu nguyên lý hoạt động của AWS PrivateLink và hai loại VPC Endpoints: Gateway Endpoint và Interface Endpoint.
  * Triển khai thành công kết nối tới Amazon S3 qua Gateway Endpoint từ Private Subnet, giúp lưu lượng truy cập luôn nằm trong mạng nội bộ AWS và tiết kiệm chi phí băng thông NAT Gateway.
  * Cấu hình Interface Endpoint cho phép môi trường tại chỗ (On-premises) truy cập bảo mật tài nguyên đám mây thông qua Private IP nội bộ.
  * Thiết lập chặt chẽ chính sách VPC Endpoint Policy để ngăn ngừa thất thoát dữ liệu (data exfiltration), bảo đảm an toàn tuân thủ các tiêu chuẩn bảo mật khắt khe.
