# 📘 Module 8: Lấy Dữ liệu từ Jira & Git để "Nói chuyện" với AI

## 🎯 Mục tiêu của Module

Sau khi hoàn thành module này, học viên có thể:

- Hiểu và áp dụng được các phương pháp trích xuất dữ liệu từ Jira thông qua các chức năng export cơ bản.
- Nắm vững cách đọc và diễn giải dữ liệu từ Git log để hiểu lịch sử phát triển dự án.
- Biết cách kết hợp và tham chiếu dữ liệu từ nhiều nguồn khác nhau (Jira, Git, Confluence, Google Drive).
- Chuẩn bị và định dạng dữ liệu phù hợp để tối ưu hóa việc phân tích bằng công cụ AI.
- Thực hiện các bước cơ bản để làm sạch và chuẩn hóa dữ liệu trước khi đưa cho AI phân tích.
- Biết cách tổ chức dữ liệu thành các định dạng mà AI có thể hiểu và xử lý hiệu quả.

---

## 📚 Nội dung chính

### 1. Cách Export dữ liệu từ Jira

- **(Dự kiến file chi tiết: `1_export_du_lieu_jira.md`)**
- Tổng quan về các loại dữ liệu có thể xuất từ Jira: Issues, Sprint Reports, Velocity Charts...
- Các phương pháp export dữ liệu từ Jira:
  - Export trực tiếp từ Board/Backlog
  - Sử dụng JQL (Jira Query Language) để lọc và export dữ liệu cụ thể
  - Export từ báo cáo Agile (Sprint Report, Burndown Chart)
- Các định dạng xuất: CSV, Excel, PDF, XML
- Thực hành export dữ liệu từ một project Jira mẫu
- Hạn chế quyền truy cập và các lưu ý khi export dữ liệu

### 2. Hiểu dữ liệu từ Git log

- **(Dự kiến file chi tiết: `2_hieu_du_lieu_git_log.md`)**
- Tổng quan về Git log và các thông tin quan trọng có thể trích xuất
- Các lệnh Git log cơ bản để xem lịch sử commit
  - `git log`
  - `git log --oneline`
  - `git log --stat`
  - `git log --graph`
- Sử dụng tham số để lọc và định dạng dữ liệu Git log:
  - Lọc theo thời gian, tác giả, nội dung
  - Định dạng đầu ra tùy chỉnh
- Trích xuất dữ liệu Git log sang CSV/JSON để phân tích
- Tìm hiểu các chỉ số quan trọng từ Git log: tần suất commit, thời gian commit, phân bố công việc...

### 3. Kết hợp dữ liệu từ các nguồn

- **(Dự kiến file chi tiết: `3_ket_hop_du_lieu_da_nguon.md`)**
- Tham chiếu tài liệu từ Confluence/Google Drive khi chuẩn bị dữ liệu
- Liên kết dữ liệu giữa Jira và Git:
  - Sử dụng thông tin commit từ các branch/PR được liên kết với Jira issue
  - Kết hợp thông tin tiến độ từ Jira với lịch sử thay đổi từ Git
- Kết hợp tài liệu yêu cầu từ Confluence/Google Drive với dữ liệu triển khai từ Jira/Git
- Xây dựng bức tranh toàn cảnh về dự án từ nhiều nguồn dữ liệu
- Thực hành tạo báo cáo kết hợp dữ liệu từ ít nhất 2-3 nguồn

### 4. Chuẩn bị dữ liệu để đưa cho AI

- **(Dự kiến file chi tiết: `4_chuan_bi_du_lieu_cho_ai.md`)**
- Làm sạch và chuẩn hóa dữ liệu:
  - Xử lý dữ liệu thiếu hoặc không đồng nhất
  - Loại bỏ thông tin nhạy cảm hoặc không liên quan
  - Chuẩn hóa định dạng ngày tháng, tên người dùng, v.v.
- Cấu trúc dữ liệu phù hợp với khả năng nhập của các công cụ AI:
  - Định dạng JSON, CSV, hoặc văn bản có cấu trúc
  - Phân chia dữ liệu thành các phần dễ tiêu hóa
- Tạo context rõ ràng cho AI:
  - Thêm mô tả về ý nghĩa của dữ liệu
  - Cung cấp thông tin nền tảng về dự án
  - Định rõ mục tiêu phân tích
- Kỹ thuật "chunking" dữ liệu lớn để phù hợp với giới hạn token của các mô hình AI
- Thực hành chuẩn bị một bộ dữ liệu mẫu để AI phân tích

---

## 🛠 Phương pháp giảng dạy

- **Bài giảng lý thuyết**: Giới thiệu các khái niệm và phương pháp trích xuất dữ liệu.
- **Demo thực tế**: Hiển thị quy trình export dữ liệu từ Jira và Git trong môi trường thực tế.
- **Hands-on Lab**: Học viên thực hành export dữ liệu từ project mẫu và xử lý dữ liệu.
- **Workshop**: Làm sạch, chuẩn hóa và chuẩn bị dữ liệu cho AI.
- **Case Study**: Phân tích một bộ dữ liệu mẫu từ dự án thực tế.
- **Thảo luận nhóm**: Thảo luận về thách thức và giải pháp khi làm việc với dữ liệu từ nhiều nguồn.

---

## 📝 Bài tập & Đánh giá

- **Export dữ liệu từ project Jira mẫu** theo các tiêu chí cụ thể (ví dụ: tất cả issues đã hoàn thành trong 2 Sprint gần nhất).
- **Trích xuất và phân tích Git log** từ một repository mẫu để hiểu về lịch sử phát triển.
- **Tạo một báo cáo kết hợp** dữ liệu từ Jira và Git để hiển thị tiến độ dự án.
- **Chuẩn bị một bộ dữ liệu** từ các nguồn khác nhau và định dạng phù hợp để đưa cho AI phân tích.
- **Thực hành "prompt engineering"** để AI phân tích dữ liệu đã chuẩn bị (kết hợp kiến thức từ Module 7).

---

## 📚 Tài nguyên bổ sung

- [Jira REST API Documentation](https://developer.atlassian.com/cloud/jira/platform/rest/v3/intro/)
- [Git - Viewing the Commit History](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)
- [How to Export Jira Issues to Excel and Word](https://confluence.atlassian.com/jirakb/how-to-export-jira-issues-to-excel-and-word-376763402.html)
- [Data Cleaning with Python](https://towardsdatascience.com/data-cleaning-with-python-and-pandas-detecting-missing-values-3e9c6ebcf78b)
- [OpenAI Tokenizer](https://platform.openai.com/tokenizer) - công cụ hữu ích để kiểm tra số lượng token khi chuẩn bị dữ liệu cho AI
