---
title: "Blog 2"
date: 2026-10-05
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

<h2 align="center">AMAZON TEXTRACT – VƯỢT XA VIỆC TRÍCH XUẤT VĂN BẢN TỪ TÀI LIỆU</h2>

Trong quá trình phát triển dự án hệ thống tuyển dụng, mình cần tìm hiểu giải pháp trích xuất văn bản từ các tài liệu PDF. Khi tìm hiểu những công cụ OCR truyền thống, mình nhận thấy việc nhận diện văn bản có thể gặp nhiều hạn chế, đặc biệt với tài liệu có bố cục phức tạp, bảng biểu hoặc định dạng không đồng nhất. Trong một số trường hợp mình tìm hiểu, độ chính xác chỉ khoảng 70–80%, tùy thuộc vào công cụ và tài liệu đầu vào.

Từ nhu cầu đó, mình biết đến Amazon Textract – một dịch vụ Machine Learning của AWS giúp tự động trích xuất văn bản và phân tích cấu trúc tài liệu.

Điều khiến mình chú ý không chỉ là khả năng nhận diện chữ, mà còn là cách Textract có thể chuyển nội dung trong tài liệu thành dữ liệu có cấu trúc để ứng dụng tiếp tục xử lý.

### 1. BỐI CẢNH VÀ HẠN CHẾ CỦA OCR TRUYỀN THỐNG

Các công cụ OCR thông thường tiếp cận tài liệu bằng cách quét hình ảnh và cố gắng nhận diện từng ký tự đơn lẻ. Cách tiếp cận này bộc lộ những hạn chế rõ rệt:

* Tài liệu đa cột: Thứ tự đọc dễ bị xáo trộn giữa các cột, làm thay đổi ý nghĩa của đoạn văn bản.
* Dữ liệu dạng biểu mẫu: Khó phân biệt giữa tiêu đề trường thông tin và giá trị người dùng điền vào.
* Dữ liệu dạng bảng: Bị dàn phẳng thành chuỗi văn bản liên tục, làm mất mối liên kết giữa hàng và cột.
* Bố cục biến thiên: Tài liệu thực tế thường không theo một khuôn mẫu cố định, khiến các phương pháp dựa trên tọa độ cứng không mang lại hiệu quả cao.

Để giải quyết bài toán này, Amazon Textract mang đến giải pháp nhận diện và phân tích cấu trúc tài liệu tự động mà không cần xây dựng toàn bộ quy trình tiền xử lý phức tạp.

### 2. TỔNG QUAN VỀ AMAZON TEXTRACT

Amazon Textract là dịch vụ Machine Learning của AWS được phát triển để đọc và hiểu tài liệu tương tự như con người.

Khác với OCR cơ bản chỉ trả về chuỗi văn bản thô, Textract phân tích cấu trúc không gian của tài liệu và trả về thông tin chi tiết từng thành phần: trang, dòng, từ, cặp trường thông tin và giá trị, bảng biểu và từng ô dữ liệu. Mỗi thành phần đều đi kèm tọa độ vị trí xuất hiện trên trang cùng điểm tin cậy của kết quả nhận diện.

### 3. NHỮNG TÍNH NĂNG NỔI BẬT CỦA AMAZON TEXTRACT

Textract cung cấp nhiều tính năng hữu ích phục vụ đa dạng nhu cầu xử lý:

* **Text Detection – Nhận diện văn bản:** Textract có thể nhận diện văn bản in và chữ viết tay trong các tài liệu, hình ảnh được hỗ trợ. Kết quả không chỉ bao gồm nội dung văn bản mà còn có thông tin về vị trí xuất hiện trên trang. Đây là chức năng phù hợp khi ứng dụng cần chuyển nội dung từ tài liệu sang dữ liệu số để tìm kiếm, lưu trữ hoặc xử lý tiếp.
* **Form Extraction – Trích xuất biểu mẫu:** Một điểm đáng chú ý là Textract có thể nhận diện mối quan hệ giữa trường thông tin và giá trị tương ứng, hay còn gọi là key-value pairs. Ví dụ, từ một biểu mẫu có nội dung Name: Nguyen Van A, hệ thống có thể xác định Name là trường thông tin và Nguyen Van A là giá trị tương ứng, thay vì chỉ trả về một chuỗi văn bản liên tục.
* **Table Extraction – Trích xuất bảng biểu:** Textract có khả năng nhận diện bảng, hàng, cột và nội dung trong từng ô. Nhờ đó, dữ liệu có cấu trúc trong tài liệu có thể được chuyển thành định dạng thuận tiện hơn cho các bước xử lý tiếp theo. Tính năng này hữu ích trong các bài toán xử lý báo cáo, hóa đơn, bảng dữ liệu và những tài liệu chứa nhiều thông tin dạng bảng.
* **Queries – Trích xuất thông tin theo câu hỏi:** Đây là một trong những tính năng mình thấy thú vị nhất. Thay vì chỉ yêu cầu hệ thống đọc toàn bộ tài liệu, Queries cho phép chỉ định thông tin cần tìm bằng câu hỏi bằng ngôn ngữ tự nhiên. Ví dụ, với một tài liệu phù hợp, ứng dụng có thể đặt câu hỏi như:
  * What is the customer name?
  * What is the invoice date?
  * What is the total amount?
  Textract sẽ tìm thông tin tương ứng và trả về kết quả riêng cho từng truy vấn. Tính năng này giúp ứng dụng tập trung vào dữ liệu cần thiết mà không phải tự xử lý toàn bộ văn bản theo cách thủ công.
* **Layout và Signature Detection:**
  * Layout: Nhận diện các thành phần như tiêu đề, đoạn văn, danh sách, bảng và số trang, giúp giữ lại thông tin về bố cục tài liệu.
  * Signature Detection: Phát hiện vị trí chữ ký trong tài liệu và trả về thông tin vị trí cùng điểm tin cậy của kết quả nhận diện. Các tính năng này mở rộng khả năng ứng dụng Textract trong quy trình xử lý tài liệu, kiểm tra hồ sơ và tự động hóa nghiệp vụ.

### 4. MỘT SỐ API ĐÁNG CHÚ Ý

Amazon Textract cung cấp nhiều API phục vụ các nhu cầu khác nhau:

* **DetectDocumentText:** Nhận diện văn bản thông thường.
* **AnalyzeDocument:** Phân tích văn bản, biểu mẫu, bảng, bố cục và truy vấn thông tin.
* **AnalyzeExpense:** Trích xuất dữ liệu liên quan đến hóa đơn và biên lai.
* **AnalyzeID:** Trích xuất thông tin từ một số giấy tờ định danh được hỗ trợ.
* **Analyze Lending:** Phân loại và phân tích các bộ hồ sơ vay vốn theo quy trình của dịch vụ.

Tùy trường hợp sử dụng, ứng dụng có thể chọn xử lý đồng bộ để nhận kết quả nhanh hoặc xử lý bất đồng bộ cho các tài liệu nhiều trang và khối lượng công việc lớn.

### 5. NHỮNG ĐIỀU CẦN LƯU Ý

Dù sở hữu nhiều tính năng hữu ích, Textract không đồng nghĩa với việc mọi tài liệu đều được nhận diện chính xác tuyệt đối. Kết quả còn phụ thuộc vào chất lượng tài liệu, ngôn ngữ, bố cục và loại thông tin cần trích xuất.

Một đặc điểm hữu ích là Textract trả về confidence score cho các kết quả nhận diện, giúp ứng dụng xây dựng quy tắc kiểm tra hoặc yêu cầu xác minh thủ công khi cần thiết. Tuy nhiên, điểm tin cậy không nên được xem là bảo đảm tuyệt đối rằng thông tin đã chính xác.

Bên cạnh đó, cần lựa chọn đúng API, kiểm tra khả năng hỗ trợ đối với loại tài liệu và ngôn ngữ sử dụng, đồng thời cân nhắc chi phí theo khối lượng xử lý.

### 6. KẾT LUẬN

Việc tìm hiểu Amazon Textract trong quá trình phát triển dự án giúp mình mở rộng góc nhìn về khả năng ứng dụng AI và Machine Learning trong xử lý tài liệu.

Textract không chỉ dừng lại ở OCR mà còn hỗ trợ nhận diện cấu trúc, trích xuất dữ liệu từ biểu mẫu và bảng, truy vấn thông tin theo câu hỏi, cũng như xử lý các loại tài liệu chuyên biệt.

Đây là một dịch vụ đáng tìm hiểu khi xây dựng các ứng dụng cần tự động hóa việc đọc và xử lý tài liệu, đặc biệt khi muốn tích hợp những khả năng này vào hệ thống thông qua API thay vì tự xây dựng toàn bộ pipeline nhận diện từ đầu.

### Tài liệu tham khảo

* Amazon Textract Features: [https://aws.amazon.com/textract/features/](https://aws.amazon.com/textract/features/)
* Amazon Textract Developer Guide: [https://docs.aws.amazon.com/textract/latest/dg/](https://docs.aws.amazon.com/textract/latest/dg/)
* Analyzing Documents: [https://docs.aws.amazon.com/textract/latest/dg/how-it-works-analyzing.html](https://docs.aws.amazon.com/textract/latest/dg/how-it-works-analyzing.html)

#AWS #AmazonTextract #OCR #MachineLearning #AI #DocumentProcessing #AWSStudyGroup

Link bài viết: [https://www.facebook.com/share/p/1DTpmyx7i3/](https://www.facebook.com/share/p/1DTpmyx7i3/)
