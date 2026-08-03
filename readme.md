https://app.justdone.ai/tools/ai_content_detector

4.2 Triển khai hệ thống

4.2.1 Triển khai Crawler Service

    - Thu thập dữ liệu bằng Selenium

    - Chuẩn hóa dữ liệu

    - Sinh Vector Embedding

    - Lưu vào ChromaDB

4.2.2 Triển khai Chat Service

    - Kết nối WebSocket

    - Sinh Embedding câu hỏi

    - Semantic Search trên ChromaDB

    - Xây dựng Prompt

    - Gọi OpenAI

    - Streaming Response

4.2.3 Triển khai Speech-to-Text

    - Thu âm

    - Gửi audio

    - OpenAI STT

    - Hiển thị kết quả

4.2.4 Triển khai Text-to-Speech

    - Chuẩn hóa nội dung đọc

    - Sinh audio

    - Streaming audio

    - Phát trên giao diện

4.2.5 Triển khai Authentication và Authorization

    - Login

    - JWT

    - User-Role-Resource

    - Gateway kiểm tra quyền

4.2.6 Triển khai Chat Session

    - Lưu lịch sử chat

    - Hiển thị lịch sử

    - Tiếp tục cuộc hội thoại

4.2.7 Triển khai Docker Compose

    - docker-compose.yml

    - Network

    - Volume

    - Khởi động toàn bộ hệ thống

CHƯƠNG 5. THỰC NGHIỆM VÀ ĐÁNH GIÁ (20–25 trang)
5.1 Môi trường thực nghiệm
CPU
RAM
Python
Model
5.2 Bộ dữ liệu
Bao nhiêu trang
Bao nhiêu môn học
Bao nhiêu chunk
5.3 Đánh giá Crawler
Độ đầy đủ
Thời gian
Tỷ lệ lỗi
5.4 Đánh giá Embedding

So sánh

BGE
E5
OpenAI
5.5 Đánh giá Retrieval
Recall@k
Precision@k
Hit Rate
MRR
5.6 Đánh giá Chatbot

Bộ câu hỏi kiểm thử

Thông tin học phần
Điều kiện tiên quyết
Mô tả môn học
Số tín chỉ
5.7 So sánh kết quả
LLM không dùng RAG
LLM có RAG
5.8 Đánh giá trải nghiệm người dùng

Khảo sát sinh viên

Thang đo Likert

5.9 Phân tích ưu điểm và hạn chế
CHƯƠNG 6. KẾT LUẬN VÀ HƯỚNG PHÁT TRIỂN (6–8 trang)
6.1 Kết quả đạt được
Xây dựng hệ thống hoàn chỉnh
Thu thập dữ liệu
Xây dựng Vector Database
Xây dựng chatbot
6.2 Hạn chế
Chưa cập nhật dữ liệu tự động
Chưa tối ưu Retrieval
Chưa hỗ trợ đa ngôn ngữ
6.3 Hướng phát triển
Hybrid Search
Re-ranking
Fine-tuning
Voice Chatbot
Knowledge Graph
Agentic RAG
MCP
PHỤ LỤC
Phụ lục A

Hướng dẫn cài đặt

Phụ lục B

Source Code

Crawler
Embedding
RAG
API
Phụ lục C

Prompt đầy đủ

Phụ lục D

Danh sách học phần đã thu thập

Phụ lục E

Kết quả kiểm thử

Phụ lục F

Một số đoạn mã quan trọng

TÀI LIỆU THAM KHẢO

Nên có từ 50–80 tài liệu, bao gồm:

Sách và bài báo về AI, NLP, Machine Learning.
Các công trình về LLM, RAG, Vector Database và Semantic Search.
Tài liệu chính thức của LangChain, Chroma, Hugging Face và các mô hình embedding/LLM mà bạn sử dụng.
Tài liệu chính thức của Trường Đại học Bách khoa Hà Nội liên quan đến chương trình đào tạo và học phần.
Phân bổ số trang đề xuất
Chương Nội dung Số trang
Phần mở đầu Lời cảm ơn, tóm tắt, mục lục, danh mục 8–10
Chương 1 Giới thiệu đề tài 10–12
Chương 2 Cơ sở lý thuyết 25–30
Chương 3 Phân tích và thiết kế hệ thống 20–25
Chương 4 Xây dựng và triển khai hệ thống 25–30
Chương 5 Thực nghiệm và đánh giá 20–25
Chương 6 Kết luận và hướng phát triển 6–8
Phụ lục Mã nguồn, API, dữ liệu, kết quả kiểm thử 15–20
Tổng cộng 120 ± 10 trang

Đây là bố cục phù hợp với một đồ án tốt nghiệp ngành Công nghệ thông tin vì bám sát quy trình phát triển một hệ thống phần mềm hoàn chỉnh: nghiên cứu bài toán → cơ sở lý thuyết → phân tích và thiết kế → xây dựng và triển khai → thực nghiệm và đánh giá → kết luận, đồng thời phản ánh đầy đủ các thành phần kỹ thuật của hệ thống RAG mà bạn đã xây dựng.
