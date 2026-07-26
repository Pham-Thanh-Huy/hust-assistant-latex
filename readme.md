https://app.justdone.ai/tools/ai_content_detector

CHƯƠNG 1. GIỚI THIỆU ĐỀ TÀI (10–12 trang)
1.1 Đặt vấn đề
Thực trạng tra cứu thông tin học phần
Khó khăn khi tìm kiếm trên website trường
Hạn chế của chatbot thông thường
Nhu cầu xây dựng trợ lý ảo chuyên biệt
1.2 Lý do chọn đề tài
Xu hướng phát triển của AI và LLM
Khả năng ứng dụng RAG trong hệ thống hỏi đáp
Ý nghĩa đối với sinh viên và nhà trường
1.3 Mục tiêu của đồ án
Mục tiêu tổng quát
Mục tiêu cụ thể
Xây dựng hệ thống thu thập dữ liệu
Xây dựng cơ sở tri thức
Triển khai chatbot
Hỗ trợ truy vấn bằng tiếng Việt
1.4 Đối tượng nghiên cứu
Website học phần HUST
Dữ liệu học phần
LLM
RAG
Embedding
Vector Database
1.5 Phạm vi nghiên cứu

Bao gồm

Thông tin học phần
Mô tả môn học
Số tín chỉ
Điều kiện tiên quyết
Chuẩn đầu ra

Không bao gồm

Đăng ký học
Điểm
Thông tin cá nhân
1.6 Phương pháp nghiên cứu
Nghiên cứu tài liệu
Khảo sát hệ thống
Thiết kế
Xây dựng
Thực nghiệm
Đánh giá
1.7 Nội dung thực hiện

Giới thiệu ngắn các chương còn lại.

CHƯƠNG 2. CƠ SỞ LÝ THUYẾT (25–30 trang)
2.1 Tổng quan về chatbot
Khái niệm
Phân loại
Chatbot truyền thống
AI Chatbot
2.2 Xử lý ngôn ngữ tự nhiên (NLP)
NLP
Tokenization
Named Entity
Semantic Search
2.3 Large Language Model
Transformer
GPT
Gemini
Llama
Qwen
2.4 Transformer Architecture
Attention
Self-Attention
Multi-head Attention
Positional Encoding
Feed Forward
Encoder
Decoder
2.5 Embedding
Khái niệm
Sentence Embedding
Text Embedding
Vector Space
2.6 Vector Database
Khái niệm
Chroma
FAISS
Milvus
Pinecone

So sánh các Vector Database

2.7 Similarity Search
Cosine Similarity
Euclidean Distance
Dot Product
Approximate Nearest Neighbor
2.8 Retrieval-Augmented Generation (RAG)
Nguyên lý
Pipeline
Retriever
Generator
Prompt
Context
2.9 LangChain Framework
Document Loader
Text Splitter
Embedding
Retriever
Chain
2.10 Web Crawling
HTTP
HTML
BeautifulSoup
Selenium
Crawl Strategy
2.11 Prompt Engineering
Zero-shot
Few-shot
System Prompt
Context Injection
2.12 Các nghiên cứu liên quan
Chatbot giáo dục
RAG
QA System
CHƯƠNG 3. PHÂN TÍCH VÀ THIẾT KẾ HỆ THỐNG (20–25 trang)
3.1 Khảo sát bài toán
Website học phần
Dữ liệu
Quy trình tra cứu
3.2 Phân tích yêu cầu
Chức năng
Crawl dữ liệu
Xử lý dữ liệu
Embedding
Lưu Vector Database
Hỏi đáp
Phi chức năng
Hiệu năng
Khả năng mở rộng
Độ chính xác
Khả năng cập nhật
3.3 Phân tích nghiệp vụ

Use Case

Actor

Sinh viên
Quản trị viên
3.4 Kiến trúc hệ thống

Mô tả đầy đủ Pipeline

Website

↓

Crawler

↓

Document

↓

Cleaning

↓

Chunking

↓

Embedding

↓

Chroma Database

↓

Retriever

↓

LLM

↓

Answer

3.5 Thiết kế dữ liệu

Document

Metadata

Collection

Chunk

3.6 Thiết kế Crawler
Crawl
Parse
Clean
Save
3.7 Thiết kế Vector Database
Collection
Metadata
Index
3.8 Thiết kế RAG Pipeline
Query EmbeddingREST
Retrieval
Prompt
Generation
3.9 Thiết kế Prompt

System Prompt

User Prompt

Context

Output Format

3.10 Thiết kế API

REST API

Endpoint

Crawl
Search
Chat
3.11 Thiết kế giao diện
Chat
Sidebar
History
CHƯƠNG 4. XÂY DỰNG VÀ TRIỂN KHAI HỆ THỐNG (25–30 trang)
4.1 Công nghệ sử dụng
Python
LangChain
Chroma
BeautifulSoup
FastAPI
React/Streamlit
Docker
4.2 Môi trường phát triển
IDE
Python
Package
GPU/CPU
4.3 Xây dựng Crawler
Crawl HTML
Parse
Chuẩn hóa dữ liệu
4.4 Tiền xử lý dữ liệu
Remove HTML
Unicode
Normalize
Chunking
4.5 Sinh Vector Embedding
Model Embedding
Batch
Vector Dimension
4.6 Xây dựng Chroma Database
Collection
Persist
Metadata
4.7 Xây dựng Retriever
Similarity Search
Top-k
MMR
4.8 Xây dựng Prompt

Prompt hoàn chỉnh

Prompt Template

4.9 Tích hợp LLM
API
Chat Model
Response
4.10 Xây dựng API
Endpoint
Request
Response
4.11 Xây dựng giao diện
Chat
Lịch sử
Hiển thị nguồn dữ liệu
4.12 Quy trình hoạt động

Flow hoàn chỉnh của hệ thống

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
