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

* Nắm vững phương thức tự động hóa và quản trị tài nguyên hạ tầng thông qua AWS Command Line Interface (AWS CLI v2): cấu hình hồ sơ, thao tác S3, SNS, IAM và khởi tạo trọn gói hạ tầng mạng VPC, EC2 bằng dòng lệnh
* Vận hành cơ sở dữ liệu phi quan hệ NoSQL Amazon DynamoDB: mô hình Key-Value/Document, chế độ dung lượng On-Demand vs Provisioned, tính nhất quán đọc dữ liệu, thiết kế GSI/LSI và lập trình CRUD bằng Python (Boto3)
* Triển khai giải pháp bộ nhớ đệm phân tán với Amazon ElastiCache (Redis): thiết kế cụm Cluster Mode Disabled vs Enabled, cấu hình các loại Endpoint kết nối, và kiểm thử lưu cache với redis-cli cùng mã nguồn Python
* Hoàn thiện chuỗi bài thực hành Networking Workshop chuyên sâu (VPC Components Deep Dive): hoạch định dải mạng RFC 1918 cho mô hình đa VPC, kết nối liên VPC qua VPC Peering và AWS Transit Gateway, cùng giải pháp bảo mật lưu lượng dịch vụ AWS với VPC Endpoints (Gateway & Interface Endpoints)

---

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu AWS CLI v2: cài đặt, cấu hình named profiles, output formats (json, yaml, text, table), và kích hoạt tính năng tự động gợi ý lệnh (`--cli-auto-prompt`)<br>- Thao tác quản lý dữ liệu và thông báo: thực hành các lệnh quản trị Amazon S3 (`mb`, `cp`, `sync`, `rb`) và tạo Topic, đăng ký Subscription, gửi tin nhắn Publish với Amazon SNS<br>- Quản lý định danh IAM qua CLI: tạo IAM Group, tạo IAM User, thêm User vào Group và quản trị Access Keys an toàn<br>- Tự động hóa khởi tạo toàn bộ hạ tầng mạng và máy chủ: tạo VPC, Subnet, Internet Gateway, Route Table; tạo Key Pair, Security Group và launch EC2 instance (`aws ec2 run-instances`)<br>- Áp dụng kỹ thuật lọc dữ liệu đầu ra với tham số `--query` (JMESPath) và `--filter` để trích xuất thông tin chính xác, thực hành xử lý sự cố và dọn dẹp tài nguyên qua dòng lệnh | 26/10/2026 | 26/10/2026 | <https://000011.awsfcaj.com/> |
| 3 | - Tìm hiểu nền tảng cơ sở dữ liệu NoSQL Amazon DynamoDB: mô hình Key-Value và Document (Tables, Items, Attributes), quy tắc đặt tên và các kiểu dữ liệu hỗ trợ<br>- Phân biệt hai chế độ quản lý năng lực: On-Demand Mode và Provisioned Mode (tính toán RCU, WCU); nắm vững cơ chế nhất quán dữ liệu khi đọc: Eventually Consistent Reads vs Strongly Consistent Reads<br>- Thiết kế chỉ mục phụ: Local Secondary Index (LSI) và Global Secondary Index (GSI); phân tích sự khác biệt về hiệu năng và chi phí giữa Query vs Scan<br>- Thực hành thao tác dữ liệu: tạo bảng DynamoDB, thực hiện các thao tác PutItem, GetItem, UpdateItem, DeleteItem; viết script Python với thư viện `boto3` để tự động hóa tương tác và truy vấn bảng | 27/10/2026 | 27/10/2026 | <https://000060.awsfcaj.com/> |
| 4 | - Tìm hiểu kiến trúc bộ nhớ đệm In-Memory với Amazon ElastiCache: vai trò của Caching, các khái niệm Clusters, Nodes và Shards cho Redis engine<br>- Phân biệt và thực hành cấu hình hai chế độ cụm Redis:<br>&nbsp;&nbsp;+ **Cluster Mode Disabled**: cấu hình 1 Primary Node và các Read Replicas phục vụ chia tải đọc<br>&nbsp;&nbsp;+ **Cluster Mode Enabled**: phân mảnh dữ liệu qua nhiều Shards để mở rộng quy mô ghi ngang<br>- Nắm vững và phân biệt các loại Endpoint kết nối: Primary Endpoint, Reader Endpoint, Configuration Endpoint và Node Endpoints<br>- Triển khai cụm ElastiCache Redis trong Private Subnet của VPC; kết nối từ máy chủ EC2 nội bộ, thực hành gửi lệnh kiểm tra qua `redis-cli` (SET, GET, TTL) và viết script Python (`redis-py`) để kiểm thử lưu cache kết quả truy vấn | 28/10/2026 | 28/10/2026 | <https://000061.awsfcaj.com/> |
| 5 | - Networking Workshop (Phần 1) - VPC Components & Layout Deep Dive:<br>&nbsp;&nbsp;+ Phân hoạch không gian mạng theo chuẩn RFC 1918 (dải 10.0.0.0/8, chia subnet /16 và /24) cho mô hình doanh nghiệp đa VPC (Non-Prod, Prod, Shared Services, Datacenter)<br>&nbsp;&nbsp;+ Cấu hình chuyên sâu các thành phần lõi: Public/Private Subnets, bảng định tuyến Route Tables đa tầng, Internet Gateway (IGW) và NAT Gateway cho kết nối outbound an toàn<br>&nbsp;&nbsp;+ Thiết lập phòng thủ an ninh mạng nhiều lớp: phân biệt và cấu hình Security Groups cấp máy chủ và Network ACLs cấp mạng con<br>&nbsp;&nbsp;+ Thiết lập kết nối liên VPC bằng VPC Peering: gửi yêu cầu kết nối, cập nhật Route Tables hai chiều và áp dụng Security Group referencing | 29/10/2026 | 29/10/2026 | <https://000092.awsfcaj.com/> |
| 6 | - Networking Workshop (Phần 2) - Transit Gateway, VPC Endpoints & Tổng kết:<br>&nbsp;&nbsp;+ Triển khai AWS Transit Gateway (TGW) làm trung tâm định tuyến Hub-and-Spoke thay thế cho kiến trúc peering phức tạp; cấu hình TGW Attachments và TGW Route Tables<br>&nbsp;&nbsp;+ Bảo mật kết nối dịch vụ AWS qua VPC Endpoints (AWS PrivateLink): khởi tạo Gateway Endpoint cho Amazon S3 gắn vào Route Table Private Subnet; triển khai Interface Endpoint kết nối bảo mật qua Private IP từ VPC và mô phỏng On-premises<br>&nbsp;&nbsp;+ Thiết lập chính sách VPC Endpoint Policies nhằm kiểm soát phân quyền chặt chẽ và ngăn ngừa rủi ro rò rỉ dữ liệu<br>- Đánh giá tổng kết tuần 4: Quản trị tự động bằng AWS CLI, cơ sở dữ liệu NoSQL DynamoDB, bộ nhớ đệm ElastiCache Redis, và hạ tầng mạng nâng cao với Transit Gateway & VPC Endpoints<br>- Dọn dẹp toàn bộ tài nguyên lab | 30/10/2026 | 30/10/2026 | <https://000092.awsfcaj.com/> |

---

### Kết quả đạt được tuần 4:

* **Tự động hóa quản trị hệ thống với AWS CLI v2:**
  * Thành thạo quy trình cài đặt, cấu hình nhiều named profiles và kích hoạt tính năng `--cli-auto-prompt` giúp tra cứu cú pháp và tham số lệnh nhanh chóng.
  * Quản trị thành thạo các dịch vụ lưu trữ và nhắn tin (Amazon S3, Amazon SNS) và quản lý định danh IAM (User, Group, Access Keys) hoàn toàn thông qua giao diện dòng lệnh.
  * Làm chủ quy trình triển khai trọn gói cơ sở hạ tầng mạng VPC (VPC, Subnet, IGW, Route Table) và máy chủ EC2 bằng lệnh CLI mà không cần phụ thuộc vào AWS Management Console.
  * Nắm vững kỹ thuật trích xuất dữ liệu đầu ra nâng cao bằng JMESPath thông qua tham số `--query` và lọc trạng thái tài nguyên với `--filter`.
* **Vận hành cơ sở dữ liệu NoSQL với Amazon DynamoDB:**
  * Nắm vững kiến trúc lưu trữ phân tán, mô hình dữ liệu Key-Value và Document, cùng cơ chế băm dữ liệu theo Partition Key và Sort Key.
  * Hiểu sâu sự khác biệt giữa hai chế độ tính cước On-Demand và Provisioned để tối ưu chi phí qua RCU/WCU, đồng thời nắm rõ cơ chế nhất quán dữ liệu đọc Eventually Consistent và Strongly Consistent Reads.
  * Phân biệt rõ sự khác nhau về mặt kiến trúc và chi phí giữa Query và Scan; thiết kế thành công Global Secondary Index (GSI) và Local Secondary Index (LSI) phục vụ các mẫu truy vấn mở rộng.
  * Viết mã nguồn Python với thư viện `boto3` để tự động hóa các thao tác CRUD và truy vấn dữ liệu hiệu quả trên bảng DynamoDB.
* **Tối ưu hóa hiệu năng ứng dụng với Amazon ElastiCache (Redis):**
  * Hiểu rõ vai trò của bộ nhớ đệm In-Memory trong việc giảm tải áp lực cho cơ sở dữ liệu quan hệ phía sau và triệt tiêu độ trễ truy vấn lặp lại.
  * Phân biệt rõ ràng kiến trúc giữa **Cluster Mode Disabled** để mở rộng năng lực đọc với Read Replicas và **Cluster Mode Enabled** để phân mảnh dữ liệu qua nhiều Shards mở rộng năng lực ghi ngang.
  * Nắm vững vai trò và cách cấu hình của từng loại Endpoint: Primary Endpoint, Reader Endpoint, Configuration Endpoint và Node Endpoints.
  * Triển khai cụm Redis an toàn trong Private Subnet, kết nối thành công từ EC2 bằng `redis-cli` và lập trình Python (`redis-py`) để lưu trữ đệm dữ liệu đạt độ trễ cấp độ mili-giây.
* **Kiến trúc mạng chuyên sâu & Kết nối an toàn với Networking Workshop:**
  * Hoạch định xuất sắc không gian mạng RFC 1918 cho mô hình doanh nghiệp đa VPC (Non-Prod, Prod, Shared Services, Datacenter), thiết lập định tuyến đa tầng với Route Tables, NAT Gateway, và bảo vệ mạng hai lớp qua Security Groups & Network ACLs.
  * Làm chủ hai mô hình kết nối liên VPC: triển khai kết nối điểm - điểm với **VPC Peering** cho các trường hợp đơn giản, và mở rộng quy mô lớn với trung tâm định tuyến Hub-and-Spoke **AWS Transit Gateway (TGW)**.
  * Triển khai thành công giải pháp kết nối riêng tư AWS PrivateLink qua cả **Gateway Endpoint** định tuyến nội bộ cho Amazon S3 và **Interface Endpoint** giao tiếp qua Private IP cho kết nối từ VPC và On-premises.
  * Áp dụng chặt chẽ chính sách **VPC Endpoint Policy** để ngăn chặn triệt để nguy cơ thất thoát dữ liệu, bảo đảm an toàn tuân thủ theo tiêu chuẩn bảo mật doanh nghiệp.
