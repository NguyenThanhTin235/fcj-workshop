# ☁️ AWS First Cloud AI Journey - Internship Report

<div align="center">

[![Deploy Hugo site to GitHub Pages](https://github.com/NguyenThanhTin235/fcj-workshop/actions/workflows/hugo.yml/badge.svg)](https://github.com/NguyenThanhTin235/fcj-workshop/actions/workflows/hugo.yml)
[![Hugo Extended](https://img.shields.io/badge/Hugo-Extended_v0.134+-FF4088?logo=hugo&logoColor=white)](https://gohugo.io/)
[![AWS Study Group](https://img.shields.io/badge/AWS-Study_Group-232F3E?logo=amazon-aws&logoColor=white)](https://facebook.com/groups/awsstudygroupfcj)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

**🌐 Website Báo Cáo:** [https://main.dmnzava3due75.amplifyapp.com/](https://main.dmnzava3due75.amplifyapp.com/)

</div>

---

## 📌 Giới thiệu (Overview)

Kho lưu trữ (repository) này chứa toàn bộ nội dung và mã nguồn trang web **Báo cáo thực tập** trong chương trình **Workforce Bootcamp - First Cloud AI Journey (FCAJ)** do **Công ty TNHH Amazon Web Services (AWS) Việt Nam** tổ chức.

Website được xây dựng dựa trên nền tảng **Hugo Static Site Generator** với giao diện tài liệu chuẩn AWS (`hugo-theme-learn`), hỗ trợ đa ngôn ngữ (**Tiếng Việt** và **English**) cùng tính năng tìm kiếm văn bản và sơ đồ động.

---

## 👨‍💻 Thông tin thực tập sinh (Intern Information)

| Thông tin | Chi tiết |
| :--- | :--- |
| **Họ và tên** | Nguyễn Thành Tin |
| **MSSV** | 23110340 |
| **Email sinh viên** | [23110340@student.hcmute.edu.vn](mailto:23110340@student.hcmute.edu.vn) |
| **Email cá nhân** | [thanhtin23122@gmail.com](mailto:thanhtin23122@gmail.com) |
| **Trường** | Trường Đại học Sư phạm Kỹ thuật TP.HCM (HCMUTE) |
| **Ngành học** | Công nghệ thông tin |
| **Đơn vị thực tập** | Công ty TNHH Amazon Web Services Việt Nam |
| **Chương trình** | Workforce Bootcamp - First Cloud AI Journey (FCAJ) |
| **Thời gian thực tập** | 01/10/2026 – 01/01/2027 |

---

## 🗂️ Cấu trúc nội dung báo cáo (Report Structure)

Báo cáo được tổ chức thành 7 phần chính theo chuẩn chương trình:

```text
content/
├── 1-Worklog/              # Nhật ký công việc theo từng tuần
│   ├── 1.1-Week1/          # Tuần 1: Onboarding, AWS Account, Budgets, Support, IAM & VPC
│   ├── 1.2-Week2/          # Tuần 2: Compute EC2, IAM Roles, Storage S3 & Database RDS
│   └── 1.3-Week3/          # Tuần 3: RDS Advanced, Lightsail & Containers, Auto Scaling, CloudWatch & Route 53
├── 2-Proposal/             # Đề xuất đồ án / giải pháp kỹ thuật
├── 3-BlogsPosted/          # Các bài blog kỹ thuật đã đăng trên AWS Study Group
│   ├── 3.1-Blog1/          # Blog 1: Amazon Bedrock AgentCore Memory & Code Interpreter
│   ├── 3.2-Blog2/          # Blog 2: (Đang cập nhật)
│   └── 3.3-Blog3/          # Blog 3: (Đang cập nhật)
├── 4-EventParticipated/    # Các sự kiện công nghệ, hội thảo, meetup đã tham gia
├── 5-Workshop/             # Tài liệu thực hành các bài Workshop chuyên sâu
│   ├── 5.1-workshop-overview/
│   ├── 5.2-prerequiste/
│   ├── 5.3-s3-vpc/         # Lab: Truy cập S3 từ VPC thông qua Gateway Endpoint
│   ├── 5.4-s3-onprem/      # Lab: Truy cập S3 từ môi trường On-premises qua Interface Endpoint
│   ├── 5.5-policy/         # Lab: VPC Endpoint Policies
│   └── 5.6-cleanup/        # Lab: Dọn dẹp tài nguyên
├── 6-Self-evaluation/      # Bản tự đánh giá kết quả thực tập
└── 7-Feedback/             # Đóng góp ý kiến và phản hồi
```

---

## 🛠️ Công nghệ sử dụng (Tech Stack)

* **Static Site Generator:** [Hugo](https://gohugo.io/) (phiên bản `extended` v0.120.0+)
* **Theme:** [hugo-theme-learn](https://github.com/matcornic/hugo-theme-learn) tùy biến giao diện màu sắc `workshop`
* **Ngôn ngữ nội dung:** Song ngữ Tiếng Việt (`.vi.md`) & English (`.md`)
* **Biểu đồ & Sơ đồ:** [Mermaid.js](https://mermaid.js.org/)
* **CI/CD & Hosting:**
  * **GitHub Pages:** Tự động build và deploy qua [GitHub Actions](.github/workflows/hugo.yml)
  * **AWS Amplify:** Cấu hình build tự động qua [amplify.yml](amplify.yml)

---

## 🚀 Hướng dẫn chạy cục bộ (Local Development)

### 1. Yêu cầu hệ thống (Prerequisites)
* Đã cài đặt **Git**
* Đã cài đặt **Hugo Extended** (kiểm tra bằng `hugo version`)

### 2. Cài đặt và khởi chạy
```bash
# 1. Clone repository về máy
git clone https://github.com/NguyenThanhTin235/fcj-workshop.git

# 2. Di chuyển vào thư mục dự án
cd fcj-workshop

# 3. Khởi chạy Hugo dev server (hỗ trợ hot-reload khi chỉnh sửa)
hugo server -D
```

Truy cập website tại địa chỉ:
* [http://localhost:1313/fcj-workshop/](http://localhost:1313/fcj-workshop/) (Tiếng Việt & English)

### 3. Build mã nguồn tĩnh (Build Production Bundle)
```bash
hugo --minify
```
Toàn bộ file tĩnh được tạo ra sẽ nằm trong thư mục `public/`.

---

## 🚢 Quy trình triển khai (Deployment)

Mỗi khi có commit mới được đẩy (push) lên nhánh `main`:
1. **GitHub Actions Workflow** (`.github/workflows/hugo.yml`) sẽ kích hoạt tự động.
2. Thiết lập môi trường `peaceiris/actions-hugo` phiên bản mở rộng (`extended`).
3. Thực thi lệnh build tối ưu `hugo --minify`.
4. Deploy thư mục `public/` sang nhánh `gh-pages` để xuất bản website lên GitHub Pages.

---

## 📬 Liên hệ (Contact)

* **Nguyễn Thành Tin** - [thanhtin23122@gmail.com](mailto:thanhtin23122@gmail.com)
* **GitHub:** [@NguyenThanhTin235](https://github.com/NguyenThanhTin235)
* **Cộng đồng AWS:** [AWS Study Group Facebook](https://www.facebook.com/groups/awsstudygroupfcj)
