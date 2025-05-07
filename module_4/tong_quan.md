# 📘 Module 4: Git & Quản lý Mã nguồn cho Người mới

## 🎯 Mục tiêu của Module

Sau khi hoàn thành module này, học viên có thể:

- Hiểu được vai trò và lợi ích của Git trong quản lý mã nguồn dự án phần mềm.
- Nắm vững các khái niệm cốt lõi của Git: Repository, Commit, Branch, Merge, Pull Request.
- Biết cách thực hiện các thao tác Git cơ bản trên một repository.
- Hiểu được quy trình làm việc cơ bản với Git, bao gồm cả Pull Request.
- Nhận biết cách Jira có thể được liên kết với Git để theo dõi tiến độ công việc liên quan đến mã nguồn.

---

## 📚 Nội dung chính

### 1. Giới thiệu về Git và Quản lý Phiên bản

- **Lợi ích của Git:** Tại sao cần quản lý phiên bản? Git giải quyết vấn đề gì?
- So sánh với các hệ thống quản lý phiên bản khác (nếu cần, ở mức độ rất cơ bản).
- Cài đặt Git (Windows, macOS, Linux).

### 2. Các khái niệm cốt lõi của Git

- **Repository (Kho chứa):** Local repository và Remote repository.
- **Commit:** Lưu lại các thay đổi, lịch sử commit.
- **Branch (Nhánh):** Khái niệm, tạo nhánh, chuyển nhánh, lợi ích của việc sử dụng nhánh (ví dụ: feature branch, bugfix branch).
- **Merge (Gộp nhánh):** Các kiểu merge cơ bản (Fast-forward, Three-way merge), giải quyết xung đột (conflict) khi merge.
- **HEAD, Tag, Log:** Hiểu về con trỏ HEAD, cách đánh dấu các phiên bản quan trọng bằng Tag và xem lịch sử commit.

### 3. Pull Request là gì?

- Quy trình làm việc với Pull Request (thường dùng trên các nền tảng như GitHub, GitLab, Bitbucket).
- Lợi ích của Pull Request: Code review, thảo luận, kiểm soát chất lượng mã nguồn.

### 4. Liên kết Jira với Git

- Cách Jira tích hợp với các công cụ quản lý mã nguồn như Bitbucket, GitHub, GitLab.
- Lợi ích: Liên kết commit, branch, pull request với các Issue trên Jira.
- Theo dõi trạng thái phát triển trực tiếp từ Jira.

### 5. Thực hành các lệnh Git cơ bản

- `git init`: Khởi tạo một repository mới.
- `git clone`: Sao chép một repository từ xa.
- `git status`: Xem trạng thái các file.
- `git add`: Đưa file vào staging area.
- `git commit`: Lưu thay đổi vào local repository.
- `git log`: Xem lịch sử commit.
- `git branch`: Quản lý nhánh (tạo, xóa, liệt kê).
- `git checkout`: Chuyển nhánh hoặc khôi phục file.
- `git merge`: Gộp nhánh.
- `git pull`: Cập nhật thay đổi từ remote repository.
- `git push`: Đẩy thay đổi lên remote repository.
- (Giới thiệu thêm về file `.gitignore`)

---

## 🛠 Phương pháp giảng dạy

- **Lý thuyết ngắn gọn, tập trung vào khái niệm và mục đích.**
- **Demo trực tiếp các lệnh Git trên terminal/command line.**
- **Sử dụng Git client đồ họa (ví dụ: Sourcetree, GitKraken, VS Code Git integration) để minh họa cho người mới dễ hình dung (tùy chọn).**
- **Thực hành tại chỗ (Hands-on Lab):** Học viên thực hiện các lệnh Git theo hướng dẫn.
- **Tình huống giả định:** Áp dụng Git vào một dự án nhỏ.

---

## 📝 Bài tập & Kiểm tra

- **Bài tập thực hành:**
  - Tạo một local repository.
  - Thực hiện các commit.
  - Tạo và làm việc với các branch (ví dụ: `develop`, `feature/them-chuc-nang-A`).
  - Merge các branch lại với nhau.
  - (Nâng cao hơn nếu có thời gian) Tạo một remote repository (ví dụ trên GitHub) và thực hành `push`, `pull`, tạo Pull Request.
- **Trắc nghiệm ngắn (7-10 câu):** Kiểm tra kiến thức về các khái niệm Git và ý nghĩa các lệnh cơ bản.

---

## 📌 Tài liệu tham khảo

- Trang chủ Git: [https://git-scm.com/](https://git-scm.com/)
- Sách Pro Git (Tiếng Việt hoặc Tiếng Anh): [https://git-scm.com/book/vi/v2](https://git-scm.com/book/vi/v2) hoặc [https://git-scm.com/book/en/v2](https://git-scm.com/book/en/v2)
- Atlassian Git Tutorials: [https://www.atlassian.com/git/tutorials](https://www.atlassian.com/git/tutorials)
- GitHub Skills: [https://skills.github.com/](https://skills.github.com/)
- Learn Git Branching (Interactive): [https://learngitbranching.js.org/](https://learngitbranching.js.org/)
