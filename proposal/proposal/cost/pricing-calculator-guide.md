# HƯỚNG DẪN TẠO DỰ TOÁN TRÊN AWS PRICING CALCULATOR
## Hệ thống AI CV Screening Portal (Kiến trúc v12.0 Pure Serverless)

> **Mã tài liệu:** `DOC-COST-02` · **Phiên bản:** `2.2 (Chuẩn hóa 2 bản xuất AWS Pricing Calculator chính thức)`  
> **Trang chủ công cụ:** [https://calculator.aws/](https://calculator.aws/)  
> **Bản 1 — Pricing Demo (100 CV/tháng):** [https://calculator.aws/#/estimate?id=fbd390a41c4d6d5786fef2452b89899ff8cde02e](https://calculator.aws/#/estimate?id=fbd390a41c4d6d5786fef2452b89899ff8cde02e) · Tệp đính kèm: [`Pricing Demo.json`](Pricing%20Demo.json) / [`Pricing Demo.pdf`](Pricing%20Demo.pdf)  
> **Bản 2 — Production SMB Pricing (2.000 CV/tháng):** [https://calculator.aws/#/estimate?id=b88f16b1a3adbc422df267b8ddd3724e74ed9dfe](https://calculator.aws/#/estimate?id=b88f16b1a3adbc422df267b8ddd3724e74ed9dfe) · Tệp đính kèm: [`Production SMB Pricing.json`](Production%20SMB%20Pricing.json) / [`Production SMB Pricing.pdf`](Production%20SMB%20Pricing.pdf)  
> **Region áp dụng:** `US East (N. Virginia)` / `US East (Ohio)`  
> **Tài liệu tham chiếu:** [cost-estimation.md](cost-estimation.md) · [system-architecture.md](../architecture/system-architecture.md)

Tài liệu này cung cấp chỉ dẫn chi tiết từng bước (Step-by-step Input Guide) được thiết kế **song song 2 tình huống (Side-by-side Scenarios)**:
1. **Tình huống 1: Kịch bản A — Demo / Workshop / Thử nghiệm** (100 CVs / tháng, tối ưu $0.00 mạng, tắt WAF, tối đa Free Tier).
2. **Tình huống 2: Kịch bản B — Doanh nghiệp vừa / Production SMB** (2.000 CVs / tháng, bật AWS WAF 6 lớp bảo vệ, lưu lượng thực tế).

---

## 1. Cấu hình Khởi tạo Chung (General Settings)

1. Truy cập [AWS Pricing Calculator](https://calculator.aws/) $\rightarrow$ Chọn **Create estimate**.
2. Đặt tên ước tính (Estimate Name):
   * *Nếu làm kịch bản Demo:* `Pricing Demo` (hoặc `AI CV Portal - Workshop Demo`).
   * *Nếu làm kịch bản SMB:* `AI CV Portal - Production SMB`.
3. Khu vực mặc định (Default Region): Chọn **US East (N. Virginia) `us-east-1`**.
4. Sử dụng nút **`+ Add service`** để lần lượt cấu hình các dịch vụ bên dưới.

---

## 2. Bảng Tra Cứu Nhanh Thông Số Song Song 2 Tình Huống (Master Matrix)

| Dịch vụ AWS | Trường nhập liệu trên Calculator | Tình huống 1: Demo / Workshop (100 CV) | Tình huống 2: Doanh nghiệp vừa SMB (2.000 CV) | Đơn vị (Unit) / Lưu ý |
| :--- | :--- | :---: | :---: | :--- |
| **1. AWS Lambda** | • Architecture<br>• Ephemeral storage<br>• Number of requests<br>• Allocated memory / Duration | `Arm` (hoặc `x86`)<br>`512` MB<br>**`2,500`**<br>`256` MB / `200` ms | `Arm` (hoặc `x86`)<br>`512` MB<br>**`50,000`**<br>`256` MB / `200` ms | per month<br>Free Tier: **$0.00** cả 2 kịch bản |
| **2. API Gateway** | • REST API: Requests<br>• Cache memory size<br>• WebSocket: Messages<br>• Avg connection duration<br>• Avg connection rate | **`2,500`**<br>`None`<br>**`500`**<br>`10` minutes<br>**`5`** per day | **`50,000`**<br>`None`<br>**`10,000`**<br>`15` minutes<br>**`67`** per day | exact number<br>None (tránh phí cache)<br>exact number<br>Dropdown chọn `per day` |
| **3. CloudFront** | • Flat-Rate Plans<br>• Enter quantity | `Free Plan`<br>**`1`** | `Free Plan`<br>**`1`** | Miễn phí 1 TB transfer out<br>Chi phí: **$0.00** |
| **4. AWS WAF** | • Web ACLs utilized<br>• Managed Rule Groups<br>• Custom Rules added<br>• Requests analyzed | **`0`** *(Tắt WAF ở Demo)*<br>`0`<br>`0`<br>`0` | **`1`**<br>**`5`** (Core, SQLi, Bot...)<br>**`1`** (Rate Limit)<br>**`0.05`** million | per month<br>Demo: **$0.00**<br>SMB: **~$11.03 / tháng** |
| **5. Cognito** | • User Pools: MAU<br>• Advanced security<br>• SAML / OIDC | **`100`**<br>**`Disabled`**<br>`0` | **`1,500`**<br>**`Disabled`**<br>`0` | Phải chọn **Disabled** để tránh phí ẩn $5.00/tháng |
| **6. Amazon S3** | • S3 Standard storage<br>• PUT, COPY, POST requests<br>• GET, SELECT requests | **`0.5`** GB<br>**`4,000`**<br>**`10,000`** | **`5.0`** GB<br>**`20,000`**<br>**`50,000`** | GB per month<br>Lifecycle xóa sau 90 ngày |
| **7. GuardDuty** | • Malware Protection for S3<br>• Total scanned size<br>• PUT requests monitored | Malware for S3<br>**`1`** GB per month<br>**`100`** per month | Malware for S3<br>**`4`** GB per month<br>**`2,000`** per month | ⚠️ Phải nhập số nguyên tròn, không nhập số thập phân |
| **8. Amazon SQS** | • Standard queue requests<br>• FIFO queue requests | **`0.01`** million<br>`0` (hoặc để trống) | **`0.05`** million<br>`0` (hoặc để trống) | Free Tier 1M reqs vĩnh viễn<br>Chi phí: **$0.00** |
| **9. EventBridge** | • Payload size<br>• EventBridge Pipes requests | `1` KB<br>**`0.01`** million | `1` KB<br>**`0.05`** million | Ingestion nội bộ: để trống<br>Pipes: Free 4M reqs |
| **10. Step Functions** | • Workflow type<br>• Workflow requests<br>• Transitions per workflow | `Standard Workflows`<br>**`100`**<br>**`8`** | `Standard Workflows`<br>**`2,000`**<br>**`8`** | Demo: **$0.00** (Free 4k st)<br>SMB: **$0.30** (16k st) |
| **11. Amazon Bedrock** | • Model Provider<br>• Selected Model<br>• Avg requests per minute<br>• Hours per day at this rate<br>• Input tokens / request<br>• Output tokens / request | Bật `Anthropic`, tắt AI21<br>`Claude Haiku 4.5`<br>`1`<br>**`0.1`** *(hoặc `1`)*<br>`2500`<br>`800` | Bật `Anthropic`, tắt AI21<br>`Claude Haiku 4.5`<br>`1`<br>**`1`** (~1.800 CVs)<br>`2500`<br>`800` | Image input: `No`<br>Prompt caching: `No`<br>Demo: **~$0.65 – $11.70**<br>SMB: **~$13.00** |
| **12. DynamoDB** | • Feature Capacity Mode<br>• Table class<br>• Data storage size | **`On-demand capacity`**<br>`Standard`<br>**`2`** GB | **`On-demand capacity`**<br>`Standard`<br>**`5`** GB | Bật ON On-Demand, tắt OFF Provisioned |
| **13. Amazon SES** | • Email messages sent | **`150`** | **`3,000`** | per month (Free Tier: $0.00 – $0.02) |
| **14. AWS KMS** | • Customer Managed Keys<br>• Symmetric requests | **`1`**<br>**`20,000`** | **`1`**<br>**`50,000`** | CMK sửa từ 5 về **1**<br>Requests sửa từ 2M về 20k/50k |
| **15. CloudWatch** | • Standard Logs: Data Ingested<br>• Alarms | **`2`** GB<br>`3` | **`5`** GB<br>`3` | Nằm trong Free Tier 5GB logs & 3 Alarms |
| **16. AWS Amplify** | • Build instance size<br>• Build minutes<br>• Data stored / Data served<br>• Number of SSR requests | `Standard`<br>**`50`** minutes<br>`1` GB / `5` GB<br>**Để trống** *(hoặc `0`)* | `Standard`<br>**`50`** minutes<br>`2` GB / `15` GB<br>**Để trống** *(hoặc `0`)* | SPA React Vite thuần túy<br>**KHÔNG có SSR requests** |
| **17. Textract** | • API Type<br>• Pages analyzed | `Detect Document Text`<br>**`200`** trang | `Detect Document Text`<br>**`4,000`** trang | Demo: **$0.30** *(Free Tier: $0.00)*<br>SMB: **$6.00** |
| **18. Secrets Manager**| • Number of secrets<br>• Duration / API calls | **`1`**<br>`30` days / `1` call | **`1`**<br>`30` days / `10` calls | Chi phí: **$0.40 / tháng** |
| **19. A2I / CloudTrail / IAM** | • Phân tích & Kiểm toán | Mặc định | Mặc định | Chi phí: **$0.00** cả 2 kịch bản |

---

## 3. Hướng Dẫn Chi Tiết Từng Dịch Vụ Với So Sánh Song Song & Xử Lý Lỗi Validator

---

### Dịch vụ 1: AWS Lambda (API Handlers, WebSocket Handlers & Worker)
* **Tìm kiếm:** `AWS Lambda` $\rightarrow$ **Configure**.
* **Cấu hình chung:** Architecture: `Arm` (hoặc `x86`), Ephemeral storage: `512 MB`, Duration: `200 ms`, Memory: `256 MB`.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Number of requests** | Nhập **`2500`** per month | Nhập **`50000`** per month |
| **Chi phí dự toán** | **$0.00 USD / tháng** | **$0.00 USD / tháng** |

> [!NOTE]
> AWS Free Tier miễn phí vĩnh viễn 1.000.000 requests và 400.000 GB-giây mỗi tháng, do đó cả 2 tình huống đều có chi phí Lambda = $0.00.

---

### Dịch vụ 2: Amazon API Gateway (REST API & WebSocket API)
* **Tìm kiếm:** `Amazon API Gateway` $\rightarrow$ **Configure**.

#### 2.1. Tab REST API:
* **REST API request units:** Chọn **`exact number`**.
* **Cache memory size (GB):** Chọn **`None`**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Requests** | Nhập **`2500`** per month | Nhập **`50000`** per month |
| **Chi phí REST API** | **$0.01 USD / tháng** | **$0.18 USD / tháng** |

#### 2.2. Tab WebSocket API:
* **WebSocket message units:** Chọn **`exact number`**.
* **Average message size:** Giữ nguyên **`32 KB`**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Messages** | Nhập **`500`** per month | Nhập **`10000`** per month |
| **Average connection duration** | Nhập **`10`** minutes | Nhập **`15`** minutes |
| **Average connection rate** | Nhập **`5`** | Unit: **`per day`** | Nhập **`67`** | Unit: **`per day`** |
| **Chi phí WebSocket API** | **$0.01 USD / tháng** | **$0.02 USD / tháng** |

> [!TIP]
> Ô *Average connection rate* trên Calculator chỉ có đơn vị tối đa là `per day`. Với Demo, nhập `5` per day ($5 \times 30 = 150$ kết nối/tháng). Với SMB, nhập `67` per day ($67 \times 30 \approx 2.000$ kết nối/tháng).

---

### Dịch vụ 3: Amazon CloudFront (Edge CDN)
* **Tìm kiếm:** `Amazon CloudFront` $\rightarrow$ **Configure**.
* Tại mục **CloudFront Flat-Rate Plans**:
  * Tìm đến gói **`Free Plan`** *(For Development and small projects)*.
  * Tại ô **Enter quantity**: Nhập **`1`** (áp dụng giống nhau cho cả 2 tình huống).
  * Các gói bên dưới (*Pro, Business, Premium*): **Để trống**.
* **Chi phí dự toán:** **$0.00 USD / tháng** (CloudFront miễn phí 1 TB data transfer out và 10.000.000 requests/tháng).

---

### Dịch vụ 4: AWS Web Application Firewall (WAF)
* **Tìm kiếm:** `AWS WAF` $\rightarrow$ **Configure**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Number of Web ACLs utilized** | **`0 per month`** *(Tắt WAF)* | **`1 per month`** *(Bật WAF 6 lớp)* |
| **Number of Managed Rule Groups** | `0` | **`5 per month`** (Core, SQLi, Bad, Rep, Bot) |
| **Number of Rules added** | `0` | **`1 per month`** (Rate Limit) |
| **Number of web requests received** | `0` | **`0.05`** million per month |
| **Chi phí WAF** | **$0.00 USD / tháng** | **~$11.03 USD / tháng** |

> [!NOTE]
> Trong mã nguồn CDK (`infra/`), hệ thống hỗ trợ cờ `enableWaf`. Ở môi trường Demo ta cấu hình `enableWaf: false` để tiết kiệm $11.03/tháng. Khi đưa lên Production ta đổi thành `enableWaf: true`.

---

### Dịch vụ 5: Amazon Cognito (User Pool)
* **Tìm kiếm:** `Amazon Cognito` $\rightarrow$ Chọn **Cognito User Pools** (Cognito Lite Tier).

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Number of monthly active users (MAU)** | Nhập **`100`** MAU | Nhập **`1500`** MAU |
| **Advanced security features** | Bắt buộc chọn: **`Disabled`** | Bắt buộc chọn: **`Disabled`** |
| **SAML / OIDC federation** | Nhập `0` | Nhập `0` |
| **Chi phí Cognito** | **$0.00 USD / tháng** | **$0.00 USD / tháng** |

> [!CAUTION]
> **Loại bỏ chi phí ẩn $5.00:** AWS Pricing Calculator mặc định bật `Advanced security features: Enabled`. Bắt buộc phải bấm đổi sang **`Disabled`** để không bị tính thêm $5.00/tháng vì hệ thống đã dùng bảo mật SRP Auth kết hợp WAF.

---

### Dịch vụ 6: Amazon S3 (Quarantine & Clean Storage)
* **Tìm kiếm:** `Amazon S3` $\rightarrow$ **Configure**.
* Chọn **S3 Standard**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **S3 Standard storage** | Nhập **`0.5`** GB per month | Nhập **`5.0`** GB per month |
| **PUT, COPY, POST, LIST requests** | Nhập **`4000`** requests | Nhập **`20000`** requests |
| **GET, SELECT requests** | Nhập **`10000`** requests | Nhập **`50000`** requests |
| **Chi phí S3** | **~$0.04 USD / tháng** | **~$0.12 USD / tháng** |

*(Các trường S3 Select, Data Replication để trống).*

---

### Dịch vụ 7: Amazon GuardDuty (Malware Protection for S3)
* **Tìm kiếm:** `Amazon GuardDuty` $\rightarrow$ **Configure**.
* Chọn mục **GuardDuty Malware Protection for S3**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Total Size of S3 Objects scanned** | Nhập số nguyên: **`1`** GB per month | Nhập: **`4`** GB per month |
| **Number of PUT requests monitored** | Nhập **`100`** per month | Nhập **`2000`** per month |
| **Chi phí GuardDuty** | **~$0.11 – $0.20 USD / tháng** | **~$0.80 USD / tháng** |

> [!WARNING]
> **Khắc phục lỗi Validator đỏ:** Nếu nhập `0.2` (hoặc `200` MB), Calculator sẽ báo lỗi *Total Size of S3 Objects scanned per month cannot be in decimal*. **Cách khắc phục:** Đổi Unit sang **`GB per month`** và nhập số nguyên tròn là **`1`** (cho Demo) hoặc **`4`** (cho SMB).

---

### Dịch vụ 8: Amazon SQS & EventBridge
* **Amazon SQS:**
  * **Standard queue requests:** Demo nhập **`0.01`** million; SMB nhập **`0.05`** million | Unit: `million per month`.
  * **FIFO queue requests:** Để trống cho cả 2 tình huống (hệ thống sử dụng Standard Queue kết hợp Step Functions Idempotency).
  * Chi phí: **$0.00 USD / tháng** (Free Tier 1.000.000 requests vĩnh viễn).
* **Amazon EventBridge & EventBridge Pipes:**
  * **Payload size:** `1 KB`.
  * **EventBridge Event Bus - Ingestion:** Để trống toàn bộ (sự kiện dịch vụ AWS nội bộ miễn phí $0.00).
  * **EventBridge Pipes:** Cuộn xuống mục Pipes $\rightarrow$ Ô **Number of requests:** Demo nhập **`0.01`** million; SMB nhập **`0.05`** million | Unit: `million per month`.
  * Chi phí: **$0.00 USD / tháng** (Free Tier 4.000.000 requests/tháng).

---

### Dịch vụ 9: AWS Step Functions (Standard Workflow)
* **Tìm kiếm:** `AWS Step Functions` $\rightarrow$ **Configure**.
* Chọn **Standard Workflows**.
* **State transitions per workflow:** Nhập **`8`** cho cả 2 tình huống (8 bước điều phối tuần tự: Claim-Check, OCR, PII Redact, Bedrock Score, Validate Schema, DynamoDB, WebSocket, SES).

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Workflow requests** | Nhập **`100`** per month | Nhập **`2000`** per month |
| **Tổng số state transitions** | $100 \times 8 = 800$ transitions | $2.000 \times 8 = 16.000$ transitions |
| **Chi phí Step Functions** | **$0.00 USD / tháng** *(Free Tier 4k st)* | **$0.30 USD / tháng** *(vượt 12k st)* |

---

### Dịch vụ 10: Amazon Bedrock (Anthropic Claude Haiku 4.5)
* **Tìm kiếm:** `Amazon Bedrock` $\rightarrow$ **Configure**.
* **Provider:** Gạt TẮT `AI21 Labs`, chỉ gạt BẬT duy nhất **`Anthropic`**.
* **Model Settings:**
  * **Inference Routing:** `Global` (hoặc `In Region`).
  * **Inference Type:** `On Demand - Standard`.
  * **Selected Model:** Chọn dropdown **`Anthropic: Claude Haiku 4.5`** *(hoặc `Claude 3.5 Haiku`)*.
  * **Average input tokens per request:** Nhập **`2500`**.
  * **Average output tokens per request:** Nhập **`800`**.
  * **Image input / Prompt caching:** Chọn **`No`**.

| Trường cấu hình | Tình huống 1: Demo (Tính theo giờ máy) | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Average requests per minute** | `1` | `1` |
| **Hours per day at this rate** | **`0.1`** *(hoặc `1`)* | **`1`** (~1.800 – 2.000 CVs/tháng) |
| **Chi phí Bedrock** | **~$0.65 – $11.70 USD / tháng** | **~$13.00 USD / tháng** |

> [!NOTE]
> Trong tệp [`Pricing Demo.json`](Pricing%20Demo.json), Bedrock được cấu hình với thông số an toàn: `1 req/phút` và `1 giờ/ngày` $\to$ chi phí ghi nhận thực tế là **`$11.70 USD / tháng`** (đáp ứng trọn vẹn cả nhu cầu Demo lẫn tải thực tế của doanh nghiệp vừa).

---

### Dịch vụ 11: Amazon DynamoDB (Single-Table On-Demand)
* **Tìm kiếm:** `Amazon DynamoDB` $\rightarrow$ **Configure**.
* > [!IMPORTANT]
  > **Chuyển chế độ tính phí On-Demand:** Tại mục **Choose DynamoDB features**:
  > * Gạt **BẬT (ON):** **`DynamoDB on-demand capacity`**.
  > * Gạt **TẮT (OFF):** **`DynamoDB provisioned capacity`**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Table class** | `Standard` | `Standard` |
| **Data storage size** | Nhập **`2`** GB | Nhập **`5`** GB |
| **Average item size** | `1 KB` | `1 KB` |
| **Chi phí DynamoDB** | **~$0.00 – $0.51 USD / tháng** | **~$0.11 – $0.55 USD / tháng** |

---

### Dịch vụ 12: Amazon Simple Email Service (SES)
* **Tìm kiếm:** `Amazon Simple Email Service (SES)` $\rightarrow$ **Configure**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Email messages sent** | Nhập **`150`** per month | Nhập **`3000`** per month |
| **Chi phí SES** | **$0.01 – $0.02 USD / tháng** | **$0.00 – $0.30 USD / tháng** |

---

### Dịch vụ 13: AWS Key Management Service (KMS)
* **Tìm kiếm:** `AWS Key Management Service (KMS)` $\rightarrow$ **Configure**.

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Number of CMKs** | **Sửa từ 5 về `1`** | **Sửa từ 5 về `1`** |
| **Number of symmetric requests** | **Sửa từ 2M về `20000`** *(Free Tier)* | **Sửa từ 2M về `50000`** |
| **Chi phí KMS** | **$1.06 USD / tháng** | **$1.09 USD / tháng** |

> [!WARNING]
> Mặc định Calculator điền sẵn là 5 CMK và 2 triệu request. Bắt buộc sửa về **`1 CMK`** (vì hệ thống dùng 1 CMK duy nhất) và **`20.000 requests`** để không bị đội chi phí vô lý.

---

### Dịch vụ 14: Amazon CloudWatch
* **Tìm kiếm:** `Amazon CloudWatch` $\rightarrow$ **Configure**.
* **Standard Logs: Data Ingested:** Demo nhập **`2 GB`**; SMB nhập **`5 GB`**.
* **Alarms:** Nhập `3` Alarms (DLQ Monitor, Error 5xx, Bedrock Quotas).
* **Chi phí dự toán:** **~$1.01 USD / tháng** (hoặc $0.00 nếu trong hạn mức Free Tier 5 GB).

---

### Dịch vụ 15: AWS Amplify (Web App Hosting)
* **Tìm kiếm:** `AWS Amplify` $\rightarrow$ Chọn **Web App Hosting** $\rightarrow$ **Configure**.
* **Select build instance size:** `Standard (8 GB Memory, 4 vCPUs)`.
* **Number of build minutes:** Nhập **`50`** per month (cho cả 2 tình huống).
* **Data stored / Data served:** Demo nhập `1 GB / 5 GB`; SMB nhập `2 GB / 15 GB`.
* > [!IMPORTANT]
  > **Xác định SSR:** Ứng dụng là **Single-Page Application (SPA) React 18 + Vite (Client-Side Rendering)**. Ô **Number of SSR requests** bạn **ĐỂ TRỐNG (hoặc `0`)**.
* **Chi phí dự toán:** **~$1.27 USD / tháng** (chưa tính trừ gói Free Tier).

---

### Dịch vụ 16: Amazon Textract (OCR Document Text)
* **Tìm kiếm:** `Amazon Textract` $\rightarrow$ **Configure**.
* Chọn **Detect Document Text API** (API bóc tách chữ từ PDF).

| Trường cấu hình | Tình huống 1: Demo / Workshop | Tình huống 2: Doanh nghiệp vừa SMB |
| :--- | :---: | :---: |
| **Number of pages analyzed** | Nhập **`200`** trang *(100 CV $\times$ 2 trang)* | Nhập **`4000`** trang *(2.000 CV $\times$ 2 trang)* |
| **Chi phí Textract** | **$0.30 USD / tháng** *(hoặc $0.00 Free)* | **$6.00 USD / tháng** |

---

### Dịch vụ 17: AWS Secrets Manager
* **Tìm kiếm:** `AWS Secrets Manager` $\rightarrow$ **Configure**.
* **Number of secrets:** `1` secret.
* **Average duration:** `30 days`.
* **Number of API calls:** Demo nhập `1`; SMB nhập `10` per month.
* **Chi phí dự toán:** **$0.40 USD / tháng** cho cả 2 tình huống.

---

### Dịch vụ 18: Các Dịch Vụ Mặc Định Miễn Phí Khác
* **AWS CloudTrail:** 1 Management event trail $\to$ **$0.00 USD**.
* **AWS IAM Access Analyzer:** 1 Analyzer kiểm toán tài khoản $\to$ **$0.00 USD**.
* **Amazon Augmented AI (A2I):** Cấu hình Private Workforce nội bộ HR $\to$ **$0.00 USD**.

---

## 4. Tổng Hợp & So Sánh Ngân Sách Song Song 2 Tình Huống

| Chỉ số FinOps cốt lõi | Tình huống 1: Demo / Workshop (100 CV) | Tình huống 2: Doanh nghiệp SMB (2.000 CV) |
| :--- | :---: | :---: |
| **Tên bản dự toán AWS** | **`Pricing Demo`** | **`Production SMB Pricing`** |
| **Quy mô hồ sơ xử lý** | **100 hồ sơ / tháng** | **2.000 hồ sơ / tháng** |
| **Chi phí hàng tháng (Monthly Cost)** | **`$18.63 USD / tháng`** *(theo file export)* | **`$28.08 USD / tháng`** *(theo file export)* |
| **Chi phí cả năm (12 Months)** | **`$223.56 USD / năm`** | **`$336.96 USD / năm`** |
| **Chi phí ban đầu (Upfront)** | **`$0.00 USD`** | **`$0.00 USD`** |
| **Đơn giá xử lý trên 1 CV (Unit Cost)** | ~$0.186 USD / CV (tải nhỏ) | **~$0.014 USD / CV (~350 VNĐ / CV)** |
| **Mức độ tiết kiệm so với VPC Enterprise** | **Tiết kiệm 98.5%** | **Tiết kiệm 95.2%** |

---

## 5. Báo Cáo & Tệp Dự Toán Đã Lưu Trữ

### Bản 1: Pricing Demo (Môi trường Thử nghiệm / Workshop)
* **Public Share URL chính thức:** [https://calculator.aws/#/estimate?id=fbd390a41c4d6d5786fef2452b89899ff8cde02e](https://calculator.aws/#/estimate?id=fbd390a41c4d6d5786fef2452b89899ff8cde02e)
* **Tệp JSON chi tiết:** [`Pricing Demo.json`](Pricing%20Demo.json)
* **Tệp PDF báo cáo AWS:** [`Pricing Demo.pdf`](Pricing%20Demo.pdf)
* **Tổng chi phí:** **$18.63 USD / tháng** ($223.56 USD / năm).

### Bản 2: Production SMB Pricing (Môi trường Doanh nghiệp vừa)
* **Public Share URL chính thức:** [https://calculator.aws/#/estimate?id=b88f16b1a3adbc422df267b8ddd3724e74ed9dfe](https://calculator.aws/#/estimate?id=b88f16b1a3adbc422df267b8ddd3724e74ed9dfe)
* **Tệp JSON chi tiết:** [`Production SMB Pricing.json`](Production%20SMB%20Pricing.json)
* **Tệp PDF báo cáo AWS:** [`Production SMB Pricing.pdf`](Production%20SMB%20Pricing.pdf)
* **Tổng chi phí:** **$28.08 USD / tháng** ($336.96 USD / năm).

