UC04 - Text To Speech
Thông tin chung
Thuộc tính	Nội dung
Tên	Text To Speech
Actor	User
Mục đích	Chuyển đổi câu trả lời của chatbot thành giọng nói
Tiền điều kiện	Chatbot đã tạo câu trả lời dạng văn bản
Hậu điều kiện	Người dùng nghe được câu trả lời thông qua dữ liệu âm thanh
Luồng chính
Bước	Thực hiện
1	Chatbot hoàn thành câu trả lời cho User
2	Chat Service chuẩn hóa nội dung trả lời cho voice
3	Response ID và voice text được lưu vào Chat Session Service
4	FE hiển thị nút phát âm thanh bên cạnh câu trả lời
5	User nhấn nút Voice
6	FE gửi Response ID tới Gateway
7	Gateway chuyển request tới Chat Service
8	Chat Service lấy nội dung voice text tương ứng
9	Chat Service gửi text tới OpenAI Text-To-Speech Model
10	OpenAI tạo dữ liệu âm thanh
11	Chat Service streaming audio về FE
12	FE phát âm thanh cho User
Flow xử lý
Chatbot Response
 |
 v
Chat Service
 |
 | Normalize Voice Text
 v
Chat Session Service
 |
 | Save Response ID
 v
React FE
 |
 | User Click Voice
 v
Gateway
 |
 v
Chat Service
 |
 v
OpenAI TTS Model
 |
 | Generate Audio
 v
Audio Stream
 |
 v
React FE
 |
 v
Play Voice
UC05 - Xem lịch sử chat
Thông tin chung
Thuộc tính	Nội dung
Tên	Xem lịch sử chat
Actor	User
Mục đích	Cho phép người dùng xem lại các phiên hội thoại đã thực hiện
Tiền điều kiện	Người dùng đã đăng nhập
Hậu điều kiện	Danh sách và nội dung lịch sử hội thoại được hiển thị
Luồng chính
Bước	Thực hiện
1	User truy cập chức năng lịch sử chat
2	FE gửi request lấy lịch sử hội thoại
3	Gateway tiếp nhận request
4	Gateway chuyển request tới Chat Session Service
5	Chat Session Service xác định User ID
6	Service truy vấn dữ liệu trong Database
7	Database trả về danh sách phiên chat
8	Chat Session Service xử lý dữ liệu
9	Gateway trả kết quả về FE
10	FE hiển thị danh sách lịch sử chat
Flow xử lý
User
 |
 v
React FE
 |
 | Request History
 v
Gateway
 |
 v
Chat Session Service
 |
 | Query
 v
Database
 |
 | Return Data
 v
Chat Session Service
 |
 v
React FE
 |
 v
Display History
UC06 - Crawl dữ liệu học phần
Thông tin chung
Thuộc tính	Nội dung
Tên	Crawl dữ liệu học phần
Actor	Crawler Service
Mục đích	Thu thập dữ liệu học phần từ website trường và tạo dữ liệu vector phục vụ chatbot
Tiền điều kiện	Website trường có dữ liệu học phần và crawler service được kích hoạt
Hậu điều kiện	Dữ liệu học phần được chuyển thành vector embedding và lưu trong ChromaDB
Luồng chính
Bước	Thực hiện
1	Scheduler kích hoạt tiến trình crawler
2	Crawler Service khởi tạo Selenium
3	Selenium truy cập website trường
4	Crawler Service thu thập dữ liệu học phần
5	Dữ liệu được làm sạch và chuẩn hóa
6	Dữ liệu được phân đoạn thành các document
7	Crawler Service gọi OpenAI Embedding Model
8	Nhận vector embedding tương ứng
9	Lưu embedding và metadata vào ChromaDB
10	Hoàn tất quá trình cập nhật dữ liệu chatbot
Flow xử lý
Scheduler
 |
 v
Crawler Service
 |
 v
Selenium
 |
 v
University Website
 |
 v
Raw Data
 |
 v
Data Processing
 |
 v
OpenAI Embedding Model
 |
 v
Vector Embedding
 |
 v
ChromaDB
UC07 - Quản lý User Role Resource
Thông tin chung
Thuộc tính	Nội dung
Tên	Quản lý User Role Resource
Actor	Admin
Mục đích	Quản lý phân quyền truy cập API theo mô hình RBAC động
Tiền điều kiện	Admin đăng nhập thành công
Hậu điều kiện	Thông tin User, Role, Resource được cập nhật trong hệ thống
Luồng chính
Bước	Thực hiện
1	Admin truy cập chức năng quản lý phân quyền
2	FE gửi request tới Gateway
3	Gateway gọi Auth Service kiểm tra quyền
4	Auth Service xác thực JWT Token
5	Gateway chuyển request tới User Service
6	Admin thực hiện thêm, sửa, xóa User, Role hoặc Resource
7	User Service cập nhật dữ liệu
8	Database lưu thông tin thay đổi
9	User Service trả kết quả về Gateway
10	FE hiển thị kết quả xử lý
Flow xử lý
Admin
 |
 v
React FE
 |
 v
Gateway
 |
 v
Auth Service
 |
 | Check Permission
 v
User Service
 |
 | CRUD
 v
Database
 |
 v
Response
 |
 v
React FE



Tôi đang viết báo cáo đồ án tốt nghiệp về chatbot hỏi đáp về học phần của trường gồm các phần sau:

- Luồng crawler từ selenium trang của trường (viết bởi selenium và service là crawler-service), lấy dữ liệu, biến nó thành các vector ebedding qua openAI, lưu vào cơ sở dữ liệu vector Chromadb

- Khi người dùng hỏi đáp, FE  (React js) sẽ truyền câu hỏi qua websocket và chat-service (python) sẽ nhận yêu cầu, parse câu hỏi thành vector embedding, so sánh tương ứng trong csdl vector (chroma) lấy ra các dữ liệu tương ứng,  sau đó ghép vào prompt để đưa vào LLM (OPEN_AI) sau đó streaming và trả lại cho FE. Sau khi chat xong thì BE gửi tới cho chat-session-service (java spring) để thực hiện việc lưu lịch sử chat, hiển thị thông tin lịch sử chat vv....

- Còn có luồng speech - to -text khi người dùng thu âm, sẽ truyền cho BE chat-service (python), chat-service gọi model open AI, trả lại text cho bên FE hiển thị

- Luồng text-to-speech thì ngược lại, khi người dùng chat, lịch sử chat sẽ chuẩn hóa câu chat cho voice thành 1 trường riêng, phía FE sẽ hiển thị nút voice bên cạnh câu trả lời sau khi bot trả lời, rồi khi người dùng click truyền response ID đó và sẽ có được đoạn stream voice cho người dùng 

- Bên cạnh đó còn có luồng dynamic security với các quyền user-role-resource, sẽ nằm ở user-service và authen-service

user service sẽ phục vụ cho việc login, register vv.... 

authen service sẽ phục vụ cho việc khi gọi API check quyền, nếu được thì đi qua và gateway sẽ tiếp tục gọi tới các service tương ứng

quy tắc role sẽ là API - các role gì đưọc gọi - có các user nào có role đó
 - deploy sẽ bằng docker - docker compose vì nhiều service 


Tôi đã viết xong chương 1 giới thiệu, và chương 2 Cơ sở lý thuyết, giờ tôi cần tới chương 3 phân tích thiết kế hệ thống, vẽ usecase thế nào, diagram ở đâu etc.... ,  hãy giúp tôi xem cần viết các mục gì, ý gì để hoàn thành chưong này khoảng 20 - 25 trang theo hướng báo cáo đồ án, những nơi bạn chỉ mà liên quan tới use case hay diagram thì cho tôi prompt đoạn đó luôn để cho bot sinh ra mermaid import vào draw.io 