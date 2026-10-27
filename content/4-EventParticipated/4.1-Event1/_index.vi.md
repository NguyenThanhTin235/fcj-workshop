---
title: "Event 1"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

<h2 align="center">BÀI THU HOẠCH: BUỔI MEET UP FIRST CLOUD AI JOURNEY</h2>

### Mục đích sự kiện 

* Lắng nghe chia sẻ thực chiến từ các Tech Lead và kỹ sư doanh nghiệp về Cloud và AI Agent trong môi trường doanh nghiệp.
* Tìm hiểu các bài toán thực tiễn: Voice AI tiếng Việt độ trễ thấp, chia sẻ tài nguyên an toàn trong AWS Organization, pentest hạ tầng tự động bằng Security Agent, và tối ưu chi phí hạ tầng với MicroVM EC2 Spot.
* Mở rộng mạng lưới kết nối với cộng đồng kỹ sư AWS và các bạn thực tập sinh trong chương trình First Cloud AI Journey.

### Danh sách diễn giả

* **Anh Kiệt Trần** - Revve AI
* **Anh Long Huỳnh** - Styl Solution
* **Anh Thịnh Nguyễn** - Styl Solution
* **Anh Xuân An** - Leader AWS Student Builder Group HCMUTE
* **Anh Khoa Kiều** - Tech Lead ACB
* **Anh Nghi Danh** - AWS Community Builder

### Nội dung nổi bật

#### Session 1: Hear, Think, Speak - Building a Vietnamese voice-AI contact center on AWS
* **Diễn giả:** Anh Kiệt Trần (Revve AI)
* Khám phá kiến trúc Voice AI với bài toán giảm độ trễ xuống ~1.8s để nói chuyện mượt mà.
* Live demo AI gọi điện trực tiếp để phỏng vấn sơ tuyển vị trí Cloud Engineer bằng tiếng Việt cực kỳ ấn tượng và tự nhiên.

#### Session 2: AWS Resource Access Manager
* **Diễn giả:** Anh Long Huỳnh (Styl Solution)
* Cách chia sẻ tài nguyên an toàn giữa các tài khoản trong tổ chức AWS Organization.
* Giải pháp giúp tiết kiệm chi phí, gom cụm quản trị mạng và kết hợp chặt chẽ giữa IAM policy với SCP để không ai vượt quá trần quyền hạn.

#### Session 3: AWS Pentest with AWS Continuum / Security Agent
* **Diễn giả:** Anh Thịnh Nguyễn (Styl Solution)
* Bộ giải pháp đánh giá an toàn hạ tầng từ sớm: review code Terraform, gắn trực tiếp vào GitLab/GitHub PR để bắt lỗi.
* Cho Security Agent đóng vai người dùng thực để pentest tự động trên môi trường SIT/UAT trước khi deploy thật.

#### Session 4: Amazon Bedrock AgentCore
* **Diễn giả:** Anh Xuân An (Leader AWS Student Builder Group HCMUTE)
* Cái nhìn toàn diện về hai nền tảng đưa Agent lên production:
  * **Agent Runtime:** Chạy MicroVM trên EC2 Spot siêu tiết kiệm chi phí.
  * **Hệ thống Memory:** Phân tầng Short-term đồng bộ và Long-term bất đồng bộ để Agent hiểu sâu ngữ cảnh người dùng.

#### Session 5: Kiro Crew
* **Diễn giả:** Anh Khoa Kiều (Tech Lead ACB) & Anh Nghi Danh (AWS Community Builder)
* Bài toán để AI Agent chạy 24/7 hỗ trợ review code và kiểm tra hệ thống.
* Cách Kiro Crew tạo Artifacts: Tự động cào dữ liệu việc làm thực tế và dựng biểu đồ thống kê trực quan ngay trong khung chat.
* Quản trị Context Window: Cơ chế Auto Compact khi ngữ cảnh chạm ngưỡng 70% - 90% và tính năng Break down context để kiểm tra chi tiết lượng token tiêu thụ của từng thành phần.
* Quản lý Memory & Guardrails: Cách dọn dẹp các memory cũ tránh bị phình chi phí, đồng thời thiết lập lớp chặn bảo mật không để AI tự ý xóa hạ tầng hay làm lộ secret/credential của máy chủ.

### Trải nghiệm tại sự kiện

Tham gia buổi meet up First Cloud AI Journey tại Bitexco là một trải nghiệm rất ý nghĩa và bổ ích:

* **Không gian học hỏi cởi mở:** Được tiếp cận trực tiếp với các bài toán và giải pháp đang được áp dụng tại các tổ chức tài chính và công nghệ hàng đầu như ACB, Styl Solution và Revve AI.
* **Thảo luận kỹ thuật cuốn hút:** Phiên Q&A cuối giờ diễn ra rất sôi nổi, giải đáp thực tế các trăn trở khi xây dựng và vận hành giải pháp Cloud và AI trong môi trường doanh nghiệp quy mô lớn.
* **Môi trường kết nối chuyên nghiệp:** Gặp gỡ và trao đổi trực tiếp với các chuyên gia đầu ngành, các cựu thực tập sinh và các bạn học viên có chung định hướng phát triển.

### Kết quả đạt được

* Nắm vững bức tranh tổng thể về việc ứng dụng AI Agent và Cloud trong các dự án thực tế của doanh nghiệp.
* Hiểu sâu về cơ chế quản trị Context Window, phương pháp phân tầng bộ nhớ Short-term/Long-term và cách thiết lập lớp chặn bảo mật Guardrails cho Agent.
* Nắm bắt giải pháp phân quyền đa tài khoản an toàn với AWS RAM kết hợp SCP và mô hình kiểm thử bảo mật tự động shift-left trên CI/CD.
* Tích lũy thêm góc nhìn thực chiến về bài toán tối ưu chi phí hạ tầng khi chạy các tác vụ AI 24/7 bằng MicroVM trên EC2 Spot.

### Bài học rút ra

* **Tư duy đưa giải pháp lên production:** Khoảng cách giữa một sản phẩm thử nghiệm (PoC) và hệ thống chạy thực tế rất lớn, đòi hỏi phải giải quyết triệt để các bài toán về độ trễ thời gian thực, chi phí vận hành và ranh giới an toàn thông tin.
* **Chiến lược tối ưu chi phí hạ tầng:** Không nhất thiết phải sử dụng các tài nguyên lớn đắt đỏ; việc phối hợp thông minh giữa EC2 Spot, kiến trúc MicroVM và dọn dẹp bộ nhớ định kỳ có thể giúp giảm thiểu chi phí đáng kể mà vẫn đảm bảo hiệu năng.
* **Bảo mật từ khâu thiết kế (Security by Design):** Luôn áp dụng nguyên tắc đặc quyền tối thiểu và đưa khâu kiểm thử bảo mật vào sớm trong quy trình phát triển (Shift-left security), kết hợp rà soát mã nguồn tự động để ngăn ngừa rủi ro ngay từ bước Pull Request.
* **Chủ động kết nối và học hỏi:** Việc tham gia các sự kiện cộng đồng và chủ động trao đổi với các chuyên gia giúp mở rộng góc nhìn kỹ thuật, cập nhật nhanh chóng xu hướng công nghệ mới và định hướng rõ ràng hơn cho sự nghiệp.

### Một số hình ảnh khi tham gia sự kiện

![Check-in tham gia buổi meet up First Cloud AI Journey](/images/event1/event1-checkin.jpg)
<p align="center"><em>Check-in tham gia buổi meet up First Cloud AI Journey tại Bitexco</em></p>

![Các phương pháp xây dựng Voice AI](/images/event1/event1-voice-ai-methods.jpg)
<p align="center"><em>Session 1: Ba phương pháp xây dựng Voice Agent (Cascade, Speech-to-Speech, Full-duplex S2S)</em></p>

![Kiến trúc giải pháp Revve on AWS](/images/event1/event1-revve-architecture.jpg)
<p align="center"><em>Kiến trúc chi tiết hệ thống Voice-AI Contact Center trên nền tảng AWS (EKS, Amazon Bedrock, ElastiCache, RDS)</em></p>

![Không gian sự kiện và phần trình bày kiến trúc](/images/event1/event1-presentation-overview.jpg)
<p align="center"><em>Toàn cảnh không gian chia sẻ kỹ thuật tại văn phòng AWS (Bitexco Financial Tower)</em></p>
