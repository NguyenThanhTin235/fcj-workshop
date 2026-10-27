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

* Nắm vững kiến thức điện toán đám mây và thực hành khởi tạo máy chủ Amazon EC2
* Cấu hình kết nối an toàn tới EC2 và triển khai ứng dụng web mẫu
* Gán IAM Role cho EC2 truy cập dịch vụ AWS mà không cần hardcode Access Key
* Lưu trữ đối tượng và triển khai trang web tĩnh với Amazon S3
* Khởi tạo cơ sở dữ liệu quan hệ Amazon RDS trong Private Subnet và kết nối ứng dụng từ EC2

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu điện toán đám mây Amazon EC2:<br>&nbsp;&nbsp;+ Khái niệm Instance types, AMI (Amazon Machine Image), EBS Volumes<br>&nbsp;&nbsp;+ Các họ máy chủ (General Purpose, Compute, Memory Optimized)<br>- Thực hành khởi tạo EC2:<br>&nbsp;&nbsp;+ Khởi tạo EC2 Linux Instance (Amazon Linux 2023) trong Public Subnet<br>&nbsp;&nbsp;+ Tạo và quản lý Key Pair (.pem) an toàn<br>&nbsp;&nbsp;+ Cấu hình Security Group mở cổng 22 (SSH) và 80 (HTTP) | 12/10/2026 | 12/10/2026 | <https://000004.awsstudygroup.com/> |
| 3 | - Kết nối và quản trị EC2 Instance:<br>&nbsp;&nbsp;+ Kết nối EC2 qua SSH Client và EC2 Instance Connect<br>&nbsp;&nbsp;+ Quản lý Volume EBS và tạo Snapshot sao lưu dữ liệu<br>&nbsp;&nbsp;+ Tạo Custom AMI từ EC2 Instance hiện tại<br>- Triển khai ứng dụng Web trên EC2:<br>&nbsp;&nbsp;+ Cài đặt Web Server (LAMP stack / Node.js) trên Amazon Linux 2023<br>&nbsp;&nbsp;+ Triển khai ứng dụng mẫu AWS User Management<br>&nbsp;&nbsp;+ Kiểm tra truy cập ứng dụng qua Public IPv4 / Elastic IP | 13/10/2026 | 13/10/2026 | <https://000004.awsstudygroup.com/> |
| 4 | - Phân quyền ứng dụng với IAM Roles cho EC2:<br>&nbsp;&nbsp;+ Rủi ro bảo mật khi lưu trữ Access Key / Secret Key trên máy chủ<br>&nbsp;&nbsp;+ Khái niệm IAM Instance Profile và cơ chế gán IAM Role cho EC2<br>- Thực hành cấu hình IAM Role cho EC2:<br>&nbsp;&nbsp;+ Tạo S3 Bucket lưu trữ dữ liệu<br>&nbsp;&nbsp;+ Tạo IAM Role cấp quyền truy cập S3 (AmazonS3ReadOnlyAccess)<br>&nbsp;&nbsp;+ Gán IAM Role vào EC2 Instance<br>&nbsp;&nbsp;+ Kiểm tra truy vấn S3 bằng AWS CLI từ EC2 mà không cần cấu hình Access Key | 14/10/2026 | 14/10/2026 | <https://000048.awsstudygroup.com/> |
| 5 | - Dịch vụ lưu trữ đối tượng Amazon S3:<br>&nbsp;&nbsp;+ Khái niệm S3 Bucket, Object, S3 URI, độ bền 11 số 9 (99.999999999%)<br>&nbsp;&nbsp;+ Quản lý phiên bản đối tượng (Bucket Versioning) và chính sách vòng đời (Lifecycle)<br>- Thực hành Static Website Hosting trên S3:<br>&nbsp;&nbsp;+ Tạo S3 Bucket và tải lên source code website tĩnh (HTML, CSS, JS)<br>&nbsp;&nbsp;+ Bật tính năng Static Website Hosting<br>&nbsp;&nbsp;+ Cấu hình Bucket Policy cho phép Public Read và tắt Block Public Access<br>&nbsp;&nbsp;+ Kiểm tra truy cập trang web qua S3 Website Endpoint | 15/10/2026 | 15/10/2026 | <https://000057.awsstudygroup.com/> |
| 6 | - Cơ sở dữ liệu quan hệ Amazon RDS:<br>&nbsp;&nbsp;+ Khái niệm Amazon RDS và các DB Engines (MySQL, PostgreSQL, MariaDB)<br>&nbsp;&nbsp;+ Kiến trúc Multi-AZ cho tính sẵn sàng cao và Read Replicas<br>- Thực hành triển khai RDS và kết nối:<br>&nbsp;&nbsp;+ Tạo DB Subnet Group gồm các Private Subnets trong VPC<br>&nbsp;&nbsp;+ Khởi tạo RDS MySQL Database Instance trong Private Subnet<br>&nbsp;&nbsp;+ Cấu hình Security Group cho phép traffic từ EC2 tới cổng 3306 của RDS<br>&nbsp;&nbsp;+ Kết nối ứng dụng từ EC2 tới RDS database và kiểm tra thao tác dữ liệu<br>- Dọn dẹp tài nguyên (Clean up resources) | 16/10/2026 | 16/10/2026 | <https://000005.awsstudygroup.com/> |

### Kết quả dự kiến tuần 2:

* **Nền tảng điện toán đám mây với Amazon EC2:**
  * Nắm vững các tiêu chí định cỡ tài nguyên phần cứng (sizing) và các họ máy chủ EC2 (General Purpose, Compute, Memory, Storage Optimized) để lựa chọn loại instance tối ưu cho từng loại tải công việc.
  * Hiểu rõ cơ chế khởi tạo instance từ Amazon Machine Image (AMI) và hệ thống lưu trữ khối bền bỉ thông qua Amazon Elastic Block Store (EBS Volumes).
  * Khởi tạo thành công một máy chủ EC2 Amazon Linux 2023 nằm trong Public Subnet của custom VPC đã tạo từ Tuần 1.
  * Tạo và quản lý an toàn SSH Key Pair (.pem); cấu hình các quy tắc Inbound/Outbound của Security Group chỉ mở quyền truy cập giới hạn cho cổng 22 (SSH) và 80 (HTTP).
* **Quản trị từ xa & Triển khai ứng dụng trên EC2:**
  * Thành thạo thiết lập kết nối quản trị từ xa tới máy chủ EC2 thông qua SSH Client độc lập và EC2 Instance Connect trên nền tảng trình duyệt.
  * Nắm vững vòng đời quản trị EBS Volume: gắn (attach) / tháo (detach) volume, thay đổi dung lượng trực tiếp (live resizing) và sao lưu dữ liệu bền vững bằng EBS Snapshot theo thời điểm.
  * Tạo Custom AMI từ instance đang hoạt động để chuẩn hóa image phục vụ cho việc mở rộng hệ thống trong tương lai.
  * Cài đặt thành công môi trường máy chủ web (LAMP stack / Node.js) trên Amazon Linux 2023, triển khai ứng dụng mẫu AWS User Management và kiểm tra truy cập công khai qua Elastic IP.
* **Phân quyền ứng dụng qua IAM Roles cho EC2:**
  * Nhận thức rõ các rủi ro bảo mật nghiêm trọng khi lưu trữ vĩnh viễn Access Key và Secret Access Key trực tiếp trong mã nguồn ứng dụng hoặc file cấu hình máy chủ.
  * Hiểu sâu cơ chế hoạt động của IAM Instance Profile và Instance Metadata Service (IMDSv2) trong việc cấp phát thông tin xác thực tạm thời (temporary credentials) an toàn.
  * Tạo IAM Role với đặc quyền tối thiểu (`AmazonS3ReadOnlyAccess`), gán trực tiếp vào EC2 instance và kiểm tra truy vấn dữ liệu từ S3 thành công qua AWS CLI mà không cần cấu hình Access Key.
* **Lưu trữ đối tượng & Hosting website tĩnh với Amazon S3:**
  * Nắm vững các khái niệm lưu trữ nền tảng của S3: Bucket, Object, S3 URI, tính nhất quán dữ liệu (strong read-after-write consistency) cùng độ bền dữ liệu lên tới 11 số 9 (99.999999999%).
  * Áp dụng các tính năng quản trị dữ liệu nâng cao: bật Object Versioning để chống việc xóa nhầm dữ liệu và cấu hình Lifecycle Rules giữa các lớp lưu trữ S3 (Storage Classes) nhằm tối ưu chi phí.
  * Triển khai thành công website tĩnh trên S3: tải lên mã nguồn (HTML/CSS/JS), bật Static Website Hosting, cấu hình Bucket Policy cho phép Public Read, điều chỉnh Block Public Access và kiểm tra truy cập toàn cầu qua S3 Website Endpoint.
* **Quản trị cơ sở dữ liệu quan hệ với Amazon RDS:**
  * Phân biệt rõ sự khác nhau giữa việc tự quản trị cơ sở dữ liệu trên EC2 với việc sử dụng dịch vụ cơ sở dữ liệu được quản lý toàn diện Amazon RDS.
  * Nắm vững kiến trúc Multi-AZ cho tính sẵn sàng cao (failover tự động, đồng bộ) và cơ chế Read Replicas giúp mở rộng hiệu năng đọc bất đồng bộ.
  * Thiết lập DB Subnet Group chuyên biệt trải trên các Private Subnet cô lập, tuân thủ nguyên tắc bảo mật của AWS Well-Architected Framework.
  * Khởi tạo thành công phiên bản Amazon RDS MySQL/PostgreSQL; cấu hình Security Group của RDS chỉ cho phép lưu lượng truy cập Inbound tại cổng 3306 từ Security Group của EC2 web server.
  * Kết nối thành công ứng dụng web với cơ sở dữ liệu RDS, kiểm tra toàn bộ các giao dịch dữ liệu CRUD, tạo bản sao lưu thủ công (DB Snapshot) và thực hiện dọn dẹp an toàn toàn bộ tài nguyên đã tạo.
