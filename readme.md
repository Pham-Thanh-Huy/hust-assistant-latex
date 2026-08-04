CHƯƠNG 5. ĐÁNH GIÁ VÀ THỬ NGHIỆM HỆ THỐNG
5.1 Môi trường thử nghiệm

Giới thiệu ngắn gọn:

Máy tính sử dụng để triển khai
Docker Compose
OpenAI API
ChromaDB
MySQL
Trình duyệt
Môi trường phát triển

Không cần benchmark phần cứng.

5.2 Kiểm thử chức năng

Đây sẽ là phần dài nhất.

5.2.1 Kiểm thử đăng nhập
Chức năng Kết quả mong đợi Kết quả
Login đúng Đăng nhập thành công Đạt
Sai mật khẩu Báo lỗi Đạt
JWT hết hạn Yêu cầu đăng nhập lại Đạt
5.2.2 Kiểm thử Chatbot

Ví dụ khoảng 15–20 câu hỏi.

Câu hỏi Kết quả mong đợi Kết quả
Học phần CTDLGT có bao nhiêu tín chỉ? Trả đúng số tín chỉ Đạt
Học phí CNTT Trả đúng Đạt

Kèm ảnh giao diện.

5.2.3 Kiểm thử Speech-to-Text
Trường hợp Kết quả
Thu âm tiếng Việt Nhận dạng đúng
Thu âm tiếng Anh Nhận dạng đúng
Âm thanh ngắn Đạt
5.2.4 Kiểm thử Text-to-Speech
Sinh giọng nói thành công.
Streaming audio.
Phát trên giao diện.

Có ảnh.

5.2.5 Kiểm thử phân quyền

Ví dụ:

API Student Admin
/chat ✓ ✓
/crawler ✗ ✓
/user ✓ ✓
5.3 Đánh giá hệ thống

Đây là phần không cần CPU hay RAM.

5.3.1 Đánh giá chất lượng truy xuất RAG

Ví dụ:

Chuẩn bị khoảng 20 câu hỏi.

Đánh giá:

Tiêu chí Số lượng
Trả lời chính xác 18
Thiếu thông tin 2
Sai 0

Sau đó tính:

Accuracy=
20
18
​

=90%

Đây là số liệu rất dễ làm.

5.3.2 So sánh có và không có RAG

Ví dụ cùng một câu hỏi.

Không có RAG

GPT trả lời chung chung.

Có RAG

GPT trả lời đúng học phần của HUST.

Bạn chỉ cần chụp hai ảnh.

Hội đồng rất thích kiểu đánh giá này.

5.3.3 Đánh giá Prompt

Đây là phần bạn nên viết vì hệ thống có Prompt Engineering.

Ví dụ:

Prompt ban đầu

↓

GPT trả lời dài dòng.

Prompt sau tối ưu

↓

đúng định dạng
đúng dữ liệu
không bịa.

Có thể đưa bảng:

Tiêu chí Trước Sau
Đúng dữ liệu Trung bình Cao
Hallucination Có Giảm
Định dạng Không ổn định Ổn định
5.3.4 Đánh giá Semantic Search

Ví dụ.

Query:

Tôi muốn học Java.

Top 5 kết quả.

Cho thấy kết quả đều liên quan.

Đây chính là chứng minh ChromaDB hoạt động.

5.3.5 Đánh giá thời gian phản hồi

Không cần đo CPU.

Chỉ cần dùng Postman.

Ví dụ:

Chức năng Thời gian trung bình
Login 250 ms
Chat 2.3 s
STT 1.8 s
TTS 2.1 s

Các số này Postman đo được.

5.4 Đánh giá chung
Ưu điểm
Kiến trúc Microservices.
RAG giúp tăng độ chính xác.
Streaming giảm thời gian chờ cảm nhận.
Hỗ trợ Speech-to-Text.
Hỗ trợ Text-to-Speech.
Phân quyền động.
Docker Compose triển khai thuận tiện.
Hạn chế
Phụ thuộc OpenAI.
Chưa hỗ trợ cập nhật dữ liệu theo thời gian thực.
Dữ liệu còn giới hạn trong phạm vi website của trường.
Chưa tích hợp cơ chế reranking hoặc đánh giá tự động chất lượng RAG.

CHƯƠNG 6. KẾT LUẬN VÀ HƯỚNG PHÁT TRIỂN
6.1 Kết quả đạt được

Mục này tổng kết toàn bộ đồ án theo các mục tiêu ban đầu.

Có thể trình bày theo dạng đoạn văn kết hợp gạch đầu dòng.

Ví dụ:

Khảo sát và nghiên cứu các kỹ thuật xây dựng chatbot dựa trên mô hình RAG.
Xây dựng Crawler Service tự động thu thập dữ liệu từ website của Trường Đại học Bách khoa Hà Nội.
Xây dựng quy trình chuyển đổi dữ liệu thành Vector Embedding và lưu trữ trên ChromaDB.
Xây dựng Chat Service tích hợp OpenAI, Semantic Search và Prompt Engineering.
Triển khai cơ chế phản hồi theo thời gian thực bằng WebSocket Streaming.
Tích hợp Speech-to-Text và Text-to-Speech.
Xây dựng hệ thống xác thực và phân quyền theo mô hình User–Role–Resource.
Triển khai hệ thống bằng Docker Compose.
Hoàn thành giao diện Web cho phép người dùng tra cứu thông tin học phần.

Đây là mục khoảng 1 trang.

6.2 Đánh giá kết quả đạt được

Đây là phần nhận xét sau khi thử nghiệm.

Ví dụ:

Qua quá trình triển khai và thử nghiệm, hệ thống đã đáp ứng được các mục tiêu đặt ra ban đầu. Chatbot có khả năng truy xuất thông tin học phần theo ngữ nghĩa, trả lời tương đối chính xác các câu hỏi trong phạm vi dữ liệu được thu thập. Việc kết hợp RAG với mô hình ngôn ngữ lớn giúp giảm hiện tượng sinh thông tin không chính xác và nâng cao chất lượng câu trả lời.

Sau đó nhận xét thêm:

tốc độ phản hồi ổn định;
giao diện trực quan;
dễ mở rộng;
kiến trúc Microservices thuận tiện bảo trì.

Khoảng 1 trang.

6.3 Hạn chế của hệ thống

Đây là phần hội đồng rất hay hỏi, nên viết khách quan.

Ví dụ:

Dữ liệu chỉ được thu thập từ website của Trường Đại học Bách khoa Hà Nội nên phạm vi tri thức còn hạn chế.
Chất lượng câu trả lời phụ thuộc vào dữ liệu thu thập được và khả năng truy xuất của hệ thống RAG.
Hệ thống phụ thuộc vào dịch vụ OpenAI nên chịu ảnh hưởng bởi kết nối Internet và chi phí sử dụng API.
Chưa tích hợp cơ chế cập nhật dữ liệu tự động theo thời gian thực khi website của trường thay đổi.
Chưa hỗ trợ đánh giá tự động chất lượng truy xuất hoặc cơ chế reranking để tối ưu kết quả tìm kiếm.
Chưa triển khai trên môi trường Cloud để phục vụ số lượng lớn người dùng đồng thời.

Khoảng 0.5–1 trang.

6.4 Hướng phát triển

Đây là phần rất quan trọng.

Bạn có thể viết theo hướng nghiên cứu tiếp.

Ví dụ:

Mở rộng nguồn dữ liệu

Không chỉ website học phần mà còn:

lịch học;
lịch thi;
học phí;
học bổng;
ký túc xá;
tuyển sinh;
biểu mẫu.
Tự động cập nhật dữ liệu

Crawler chạy theo lịch.

Ví dụ:

mỗi ngày;
mỗi tuần.

Không cần chạy thủ công.

Tối ưu RAG

Ví dụ:

Chunking tốt hơn.
Hybrid Search.
Reranking.
Metadata Filtering.
Hỗ trợ nhiều LLM

Không chỉ OpenAI.

Có thể:

Gemini.
Claude.
Qwen.
Llama.
Phát triển đa nền tảng

Ngoài Web.

Có thể:

Android.
iOS.
Triển khai Cloud

Ví dụ

AWS.
Azure.
Google Cloud.

Khoảng 1–2 trang.

6.5 Kết luận

Đây là đoạn cuối cùng của báo cáo.

Khoảng 1 trang.

Ý chính:

Đồ án đã hoàn thành mục tiêu.
RAG giúp nâng cao chất lượng chatbot.
Microservices giúp dễ mở rộng.
Có giá trị ứng dụng trong trường đại học.
Có thể phát triển thành sản phẩm thực tế.

PHỤ LỤC
PHỤ LỤC A. Danh sách API tiêu biểu

Mục đích: Minh họa các API chính của hệ thống.

Nội dung:

API xác thực (Đăng nhập, Đăng ký, Làm mới JWT).
API Chat (gửi câu hỏi, nhận phản hồi).
API Speech-to-Text.
API Text-to-Speech.
API quản lý Chat Session (tạo phiên, lấy lịch sử, xóa lịch sử).
API Crawler (nếu có).
Ví dụ Request và Response của một số API quan trọng.
PHỤ LỤC B. Prompt sử dụng trong hệ thống

Mục đích: Minh họa cách hệ thống xây dựng Prompt khi làm việc với mô hình ngôn ngữ.

Nội dung:

System Prompt của chatbot.
Prompt Template trong mô hình RAG.
Ví dụ Context được lấy từ ChromaDB.
Prompt hoàn chỉnh gửi tới OpenAI.
Prompt chuẩn hóa nội dung cho Text-to-Speech (nếu có).
Một số ví dụ Prompt và kết quả trả về.
PHỤ LỤC C. Một số đoạn mã nguồn tiêu biểu

Mục đích: Chứng minh việc triển khai các chức năng cốt lõi của hệ thống.

Nội dung:

Đoạn mã Selenium thu thập dữ liệu.
Đoạn mã sinh Vector Embedding.
Đoạn mã truy vấn Semantic Search trên ChromaDB.
Đoạn mã xây dựng Prompt.
Đoạn mã xử lý WebSocket Streaming.
Đoạn mã Speech-to-Text.
Đoạn mã Text-to-Speech Streaming.
Đoạn mã xác thực JWT và kiểm tra quyền.

Chỉ nên chọn những đoạn mã quan trọng, không cần đưa toàn bộ mã nguồn.

PHỤ LỤC D. File cấu hình triển khai Docker Compose

Mục đích: Minh họa cách triển khai hệ thống theo kiến trúc Microservices.

Nội dung:

File docker-compose.yml.
Cấu hình các service:
API Gateway.
User Service.
Authentication Service.
Chat Service.
Chat Session Service.
Crawler Service.
MySQL.
ChromaDB.
Cấu hình Docker Network.
Cấu hình Docker Volume.
Các biến môi trường quan trọng (không bao gồm thông tin nhạy cảm như API Key hoặc mật khẩu).
