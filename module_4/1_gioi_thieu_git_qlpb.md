## 1. Giới thiệu về Git và Quản lý Phiên bản

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được **Git là gì** và tại sao **quản lý phiên bản (Version Control System - VCS)** lại quan trọng trong phát triển phần mềm.
- Nắm được những **lợi ích chính** khi sử dụng Git.
- Biết được sự khác biệt cơ bản giữa Git (phân tán) và các hệ thống quản lý phiên bản tập trung (như SVN - nếu cần đề cập).
- Có thông tin về cách **cài đặt Git** trên các hệ điều hành phổ biến (Windows, macOS, Linux).

---

### 🧩 Nội dung chi tiết

#### 1.1. Quản lý phiên bản là gì? Tại sao lại cần thiết?

Hãy tưởng tượng bạn đang viết một tài liệu quan trọng hoặc một đoạn code.

- Bạn lưu phiên bản `tailieu_v1.doc`.
- Sau đó sửa đổi, lưu thành `tailieu_v2.doc`.
- Rồi `tailieu_final.doc`, `tailieu_final_final.doc`, `tailieu_da_sua_Xong.doc`...
  Điều này trở nên rất hỗn loạn, khó theo dõi xem phiên bản nào là mới nhất, thay đổi những gì, và nếu muốn quay lại một phiên bản cũ thì làm thế nào?

Trong phát triển phần mềm, vấn đề này còn phức tạp hơn nhiều khi có nhiều người cùng làm việc trên một dự án, sửa đổi nhiều file mã nguồn.

**Hệ thống Quản lý Phiên bản (Version Control System - VCS)** ra đời để giải quyết những vấn đề này. Nó giúp:

- **Lưu trữ lịch sử thay đổi:** Ghi lại ai đã thay đổi cái gì, khi nào.
- **Khôi phục phiên bản cũ:** Dễ dàng quay lại một trạng thái ổn định trước đó nếu có lỗi xảy ra.
- **Làm việc nhóm hiệu quả:** Nhiều người có thể cùng làm việc trên một dự án mà không ghi đè lên công việc của nhau.
- **Phân nhánh (Branching) và Gộp (Merging):** Cho phép thử nghiệm tính năng mới trên một nhánh riêng biệt mà không ảnh hưởng đến sản phẩm chính, sau đó gộp lại khi hoàn thành.

#### 1.2. Git là gì?

**Git** là một **hệ thống quản lý phiên bản phân tán (Distributed Version Control System - DVCS)** miễn phí và mã nguồn mở, được tạo ra bởi Linus Torvalds (người tạo ra Linux) vào năm 2005.

- **Phân tán (Distributed):** Khác với các hệ thống tập trung (Centralized VCS như SVN), mỗi lập trình viên khi làm việc với Git sẽ có một bản sao đầy đủ (clone) của toàn bộ kho chứa (repository), bao gồm cả lịch sử thay đổi. Điều này cho phép họ làm việc độc lập, commit thay đổi vào kho chứa cục bộ của mình ngay cả khi không có mạng. Sau đó, họ có thể đồng bộ hóa những thay đổi này với kho chứa từ xa (remote repository) khi có kết nối.
- **Mạnh mẽ và Linh hoạt:** Git cung cấp nhiều tính năng mạnh mẽ cho việc phân nhánh, gộp nhánh, xử lý xung đột, giúp quản lý các dự án phức tạp.
- **Nhanh chóng:** Hầu hết các thao tác Git (commit, branch, merge) đều được thực hiện cục bộ nên rất nhanh.
- **Phổ biến:** Git đã trở thành tiêu chuẩn de-facto trong ngành phát triển phần mềm. Hầu hết các dự án mã nguồn mở và nhiều công ty lớn nhỏ đều sử dụng Git.

#### 1.3. Lợi ích của việc sử dụng Git

- **Theo dõi lịch sử thay đổi chi tiết:** Biết rõ ai, khi nào, tại sao một thay đổi được thực hiện.
- **Khả năng quay lại (Revert):** Dễ dàng hoàn tác các thay đổi không mong muốn hoặc quay về một phiên bản ổn định trước đó.
- **Hỗ trợ làm việc nhóm hiệu quả:**
  - Mỗi người có thể làm việc trên các nhánh riêng.
  - Dễ dàng gộp các thay đổi từ nhiều người.
  - Giảm thiểu xung đột và mất mát code.
- **Phân nhánh (Branching) mạnh mẽ:**
  - Tạo nhánh để phát triển tính năng mới, sửa lỗi mà không ảnh hưởng đến nhánh chính (thường là `main` hoặc `master`).
  - Thử nghiệm ý tưởng mới một cách an toàn.
- **Tăng năng suất:** Các thao tác nhanh chóng, quy trình làm việc rõ ràng giúp lập trình viên tập trung vào việc viết code.
- **Cộng đồng lớn và tài liệu phong phú:** Dễ dàng tìm kiếm sự giúp đỡ và tài liệu học tập.

#### 1.4. Git (Phân tán) vs. SVN (Tập trung) - Giới thiệu sơ lược

| Đặc điểm             | Git (Phân tán - DVCS)                                      | SVN (Tập trung - CVCS)                                    |
| -------------------- | ---------------------------------------------------------- | --------------------------------------------------------- |
| **Kho chứa**         | Mỗi người dùng có bản sao đầy đủ của kho chứa (local repo) | Chỉ có một kho chứa trung tâm (central repo) trên server  |
| **Làm việc offline** | Có thể commit, tạo nhánh, xem lịch sử khi offline          | Cần kết nối server để commit và hầu hết các thao tác khác |
| **Tốc độ**           | Nhanh hơn cho hầu hết các thao tác (vì làm việc local)     | Chậm hơn do phụ thuộc vào server và mạng                  |
| **Phân nhánh**       | Rất mạnh mẽ, dễ dàng và nhanh chóng                        | Phân nhánh nặng nề và phức tạp hơn                        |
| **Độ phức tạp**      | Có thể khó hơn để học ban đầu do nhiều khái niệm hơn       | Dễ học hơn ở mức cơ bản                                   |

Hiện nay, Git được ưa chuộng và sử dụng rộng rãi hơn nhiều so với SVN.

#### 1.5. Cài đặt Git

Git có thể được cài đặt trên Windows, macOS và Linux.

- **Windows:**
  - Tải bộ cài đặt từ trang chủ Git: [https://git-scm.com/download/win](https://git-scm.com/download/win)
  - Chạy file `.exe` và làm theo các bước hướng dẫn. Các tùy chọn mặc định thường là đủ tốt cho người mới bắt đầu.
  - Sau khi cài đặt, bạn sẽ có Git Bash (một giao diện dòng lệnh giống Linux) và Git GUI.
- **macOS:**
  - Cách dễ nhất là cài đặt Xcode Command Line Tools. Mở Terminal và gõ:
    `xcode-select --install`
  - Hoặc tải bộ cài đặt từ: [https://git-scm.com/download/mac](https://git-scm.com/download/mac)
  - Hoặc sử dụng Homebrew: `brew install git`
- **Linux (Debian/Ubuntu):**
  - Mở Terminal và gõ:
    `sudo apt update`
    `sudo apt install git`
- **Linux (Fedora):**
  - Mở Terminal và gõ:
    `sudo dnf install git`

Sau khi cài đặt, bạn có thể mở Terminal (hoặc Git Bash trên Windows) và gõ lệnh `git --version` để kiểm tra xem Git đã được cài đặt thành công chưa.

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Version Control System (VCS):** Hệ thống quản lý phiên bản.
- **Distributed Version Control System (DVCS):** Hệ thống quản lý phiên bản phân tán (ví dụ: Git).
- **Centralized Version Control System (CVCS):** Hệ thống quản lý phiên bản tập trung (ví dụ: SVN).
- **Repository (Repo):** Kho chứa, nơi lưu trữ tất cả các file của dự án và lịch sử thay đổi của chúng.
- **Local Repository:** Bản sao của kho chứa nằm trên máy tính cá nhân của bạn.
- **Remote Repository:** Kho chứa được đặt trên một server từ xa (ví dụ: trên GitHub, GitLab, Bitbucket), nơi cả nhóm có thể chia sẻ và đồng bộ code.
- **Commit (noun & verb):** (Danh từ) Một bản ghi lại các thay đổi đã được lưu vào repository. (Động từ) Hành động lưu các thay đổi vào repository.
- **Branch (Nhánh):** Một dòng phát triển độc lập trong repository.
- **Merge (Gộp):** Hành động kết hợp các thay đổi từ một nhánh này sang một nhánh khác.
- **Git Bash:** Một ứng dụng cho Windows cung cấp môi trường dòng lệnh Git.
- **Terminal:** Giao diện dòng lệnh trên macOS và Linux.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Trước khi biết về Git, bạn đã bao giờ gặp khó khăn khi quản lý các phiên bản khác nhau của một tài liệu hoặc file code chưa? Hãy chia sẻ.
- Theo bạn, lợi ích nào của Git là quan trọng nhất đối với một dự án có nhiều người tham gia?
- Tại sao việc mỗi lập trình viên có một bản sao đầy đủ của repository (local repo) lại là một ưu điểm lớn của Git?

---

### 📌 Tài liệu & Tham khảo

- Trang chủ Git: [https://git-scm.com/](https://git-scm.com/)
- Sách Pro Git (miễn phí, có bản tiếng Việt): [https://git-scm.com/book/vi/v2](https://git-scm.com/book/vi/v2)
- Atlassian Git Tutorials: [https://www.atlassian.com/git/tutorials/what-is-version-control](https://www.atlassian.com/git/tutorials/what-is-version-control)
- GitHub Guides - Hello World: [https://docs.github.com/en/get-started/quickstart/hello-world](https://docs.github.com/en/get-started/quickstart/hello-world) (Giới thiệu về Git trong ngữ cảnh GitHub)
