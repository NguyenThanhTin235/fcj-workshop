---
title: "Blog 1"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

<h2 align="center">XÂY DỰNG AI AGENT CÓ BỘ NHỚ DÀI HẠN VÀ CHẠY CODE SANDBOX VỚI AMAZON BEDROCK AGENTCORE</h2>

Khi tìm hiểu về AI Agent, mình nhận ra rằng một trợ lý AI hữu ích không chỉ cần khả năng trả lời câu hỏi mà còn cần ghi nhớ thông tin từ những lần tương tác trước và thực thi code để giải quyết các tác vụ phức tạp.

Ví dụ, một AI Agent phân tích dữ liệu cần nhớ cách người dùng muốn trình bày báo cáo, đồng thời có khả năng chạy Python để tính toán và tạo biểu đồ thay vì chỉ dự đoán kết quả.

Amazon Bedrock AgentCore cung cấp các thành phần giúp xây dựng hệ thống như vậy mà không cần tự triển khai toàn bộ hạ tầng từ đầu.

### 1. TỔNG QUAN VỀ AMAZON BEDROCK AGENTCORE

Amazon Bedrock AgentCore Memory: Hỗ trợ lưu trữ và truy xuất thông tin từ các phiên tương tác, giúp Agent duy trì bối cảnh và ghi nhớ những thông tin hữu ích.

Amazon Bedrock AgentCore Code Interpreter: Cung cấp môi trường thực thi code cô lập, cho phép Agent chạy Python, JavaScript hoặc TypeScript để xử lý dữ liệu và thực hiện các phép tính.

Điểm quan trọng là Memory và Code Interpreter đảm nhiệm hai nhiệm vụ khác nhau. Memory lưu giữ thông tin cần sử dụng lại, còn Code Interpreter thực thi code trong một phiên sandbox.

### 2. THIẾT KẾ KIẾN TRÚC HỆ THỐNG

Thử xây dựng một AI Data Assistant có khả năng phân tích file CSV và ghi nhớ cách làm việc của người dùng.

Các thành phần sử dụng:
* Amazon Bedrock: Cung cấp mô hình ngôn ngữ để hiểu yêu cầu và điều phối tác vụ.
* AgentCore Memory: Lưu và truy xuất sở thích, quy tắc phân tích.
* AgentCore Code Interpreter: Thực thi code để tính toán và tạo biểu đồ.
* Strands Agents SDK: Hỗ trợ xây dựng Agent và tích hợp công cụ.

Quy trình hoạt động:
1. Người dùng gửi yêu cầu phân tích dữ liệu.
2. Agent truy xuất bộ nhớ để tìm các quy tắc liên quan.
3. Mô hình tạo kế hoạch và code phù hợp.
4. Code Interpreter thực thi code trong sandbox.
5. Agent sử dụng kết quả thực tế để tạo báo cáo.
6. Những thông tin hữu ích được lưu vào Memory để sử dụng trong các phiên sau.

### 3. XÂY DỰNG BỘ NHỚ DÀI HẠN

Không phải toàn bộ lịch sử hội thoại đều cần được lưu trữ lâu dài. Agent nên ưu tiên những thông tin có giá trị trong các lần tương tác tiếp theo.

Ví dụ:
* Người dùng thích nhận báo cáo dưới dạng Markdown.
* Khi phân tích dữ liệu, cần kiểm tra giá trị thiếu trước khi tính toán.
* Báo cáo cần bao gồm điểm trung bình, trung vị và biểu đồ phân phối.

Khi nhận yêu cầu mới, Agent truy xuất những thông tin liên quan và bổ sung chúng vào ngữ cảnh xử lý.

### 4. THỰC THI CODE VỚI CODE INTERPRETER

LLM có thể tạo code nhưng không bảo đảm code luôn đúng hoặc an toàn. Việc thực thi trực tiếp code do AI sinh ra trên máy chủ ứng dụng có thể gây ra rủi ro về dữ liệu, tài nguyên và quyền truy cập.

AgentCore Code Interpreter cung cấp môi trường thực thi cô lập, giúp tách biệt quá trình chạy code khỏi ứng dụng chính.

Ví dụ, khi người dùng yêu cầu phân tích file scores.csv, Agent có thể:
* Đọc và kiểm tra dữ liệu.
* Xử lý các giá trị thiếu hoặc không hợp lệ.
* Tính điểm trung bình và trung vị.
* Tạo biểu đồ phân phối.
* Trả kết quả cho Agent để tổng hợp thành báo cáo.

Sandbox có thể duy trì trạng thái làm việc trong vòng đời của session. Tuy nhiên, không nên xem các file tạm hoặc biến trong sandbox là dữ liệu lưu trữ lâu dài. Nếu cần sử dụng lại file ở phiên sau, ứng dụng nên lưu file vào một kho lưu trữ phù hợp như Amazon S3.

### 5. MINH HỌA KỊCH BẢN THỰC TẾ

Giả sử trong phiên đầu tiên, người dùng yêu cầu phân tích dữ liệu điểm số và tạo báo cáo Markdown.

Sau khi hoàn thành, Agent lưu sở thích định dạng báo cáo vào AgentCore Memory.

Ở phiên tiếp theo, người dùng chỉ cần gửi file mới và yêu cầu: "Phân tích file này giống lần trước."

Agent truy xuất bộ nhớ đã lưu, sử dụng Code Interpreter để xử lý dữ liệu và tạo báo cáo theo quy tắc phù hợp mà không cần người dùng nhắc lại toàn bộ yêu cầu.

Đây chính là giá trị của việc kết hợp bộ nhớ dài hạn với khả năng sử dụng công cụ: Agent có thể duy trì bối cảnh làm việc và thực hiện các tác vụ dựa trên kết quả tính toán thực tế.

### 6. BẢO MẬT VÀ CHI PHÍ

Khi triển khai trong môi trường thực tế, cần chú ý một số vấn đề:
* Phân quyền: Người dùng chỉ được truy cập bộ nhớ và dữ liệu thuộc phạm vi được phép.
* Bảo mật code: Giới hạn tài nguyên thực thi, quyền truy cập file và kết nối mạng của sandbox.
* Quản lý bộ nhớ: Không lưu thông tin nhạy cảm không cần thiết; có cơ chế cập nhật và xóa dữ liệu phù hợp.
* Giám sát: Theo dõi lỗi thực thi, thời gian phản hồi và mức sử dụng tài nguyên.

Chi phí cũng cần được đánh giá tổng thể, bao gồm Amazon Bedrock, AgentCore Memory, Code Interpreter và các dịch vụ lưu trữ hoặc giám sát liên quan. Mức chi phí thực tế phụ thuộc vào cách sử dụng và bảng giá hiện hành của AWS.

### 7. KẾT LUẬN

Amazon Bedrock AgentCore Memory và Code Interpreter giải quyết hai nhu cầu quan trọng khi xây dựng AI Agent: duy trì thông tin qua nhiều phiên và thực thi code trong môi trường cô lập.

Kết hợp với Amazon Bedrock và một framework như Strands Agents SDK, có thể xây dựng các ứng dụng như AI Data Analyst, Coding Assistant hoặc Research Assistant mà không cần tự triển khai toàn bộ cơ chế bộ nhớ và môi trường thực thi.

### Tài liệu tham khảo

* Amazon Bedrock AgentCore: [https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/)
* AgentCore Memory: [https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/long-term-memory-long-term.html](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/long-term-memory-long-term.html)
* AgentCore Code Interpreter: [https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/code-interpreter-getting-started.html](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/code-interpreter-getting-started.html)
* Strands Agents: [https://strandsagents.com/](https://strandsagents.com/)

#AWS #AmazonBedrock #BedrockAgentCore #AIAgent #GenerativeAI #AWSStudyGroup #CodeInterpreter #LongTermMemory

Link bài viết: [https://www.facebook.com/share/p/1B8v39nAMn/](https://www.facebook.com/share/p/1B8v39nAMn/)

