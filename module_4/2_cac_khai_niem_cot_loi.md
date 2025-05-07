## 2. Các khái niệm cốt lõi của Git

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Nắm vững các khái niệm nền tảng và quan trọng nhất của Git:
  - **Repository (Local và Remote)**
  - **Working Directory, Staging Area, và Git Directory (The .git folder)**
  - **Commit**
  - **Branch**
  - **Merge**
  - **HEAD**
  - **Tag**
  - **Log**
- Hiểu được luồng làm việc cơ bản: Modify -> Stage -> Commit.

---

### 🧩 Nội dung chi tiết

Để sử dụng Git hiệu quả, bạn cần hiểu rõ các thuật ngữ và khái niệm cốt lõi của nó.

#### 2.1. Repository (Kho chứa)

Như đã đề cập, **Repository (thường gọi tắt là Repo)** là nơi Git lưu trữ tất cả các file của dự án cùng với toàn bộ lịch sử thay đổi của chúng.

Có hai loại Repository chính:

- **Local Repository (Kho chứa cục bộ):**
  - Đây là bản sao của Repository nằm trên máy tính cá nhân của bạn.
  - Khi bạn `git clone` một dự án từ một Remote Repository, bạn đang tạo một Local Repository.
  - Bạn thực hiện hầu hết các công việc (tạo nhánh, commit, xem lịch sử) trên Local Repository này. Điều này giúp Git hoạt động rất nhanh và cho phép bạn làm việc ngay cả khi không có mạng.
  - Bên trong thư mục gốc của dự án, Git quản lý Local Repository thông qua một thư mục ẩn có tên là `.git`.
- **Remote Repository (Kho chứa từ xa):**
  - Đây là Repository được lưu trữ trên một máy chủ từ xa, thường là trên các nền tảng như GitHub, GitLab, Bitbucket, hoặc một server riêng của công ty.
  - Remote Repository đóng vai trò là nơi trung tâm để cả nhóm chia sẻ code, đồng bộ hóa các thay đổi và cộng tác.
  - Bạn sẽ `git push` những thay đổi từ Local Repository của mình lên Remote Repository để chia sẻ với người khác, và `git pull` (hoặc `git fetch`) những thay đổi từ Remote Repository về Local Repository của mình để cập nhật.

#### 2.2. Ba khu vực chính của Git: Working Directory, Staging Area, Git Directory

Khi làm việc với Git trên máy tính của bạn, có ba "khu vực" chính mà các file của bạn có thể tồn tại:

1.  **Working Directory (Thư mục làm việc):**

    - Đây chính là thư mục dự án trên máy tính của bạn, nơi bạn trực tiếp chỉnh sửa, thêm, xóa các file.
    - Các file trong Working Directory có thể ở trạng thái "untracked" (Git chưa theo dõi) hoặc "tracked" (Git đã theo dõi).
    - Các file đã được theo dõi có thể ở trạng thái "modified" (đã bị thay đổi so với lần commit cuối), "staged" (đã sẵn sàng để commit), hoặc "unmodified" (chưa có thay đổi gì mới).

2.  **Staging Area (Khu vực chuẩn bị / Index):**

    - Đây là một file đặc biệt (thường nằm trong thư mục `.git`), nơi lưu trữ thông tin về những gì sẽ đi vào lần **commit** tiếp theo của bạn.
    - Khi bạn thực hiện lệnh `git add <file_name>`, bạn đang đưa một "snapshot" (ảnh chụp nhanh) của file đó từ Working Directory vào Staging Area. Điều này có nghĩa là bạn đã "đánh dấu" những thay đổi đó để chuẩn bị cho việc commit.
    - Staging Area cho phép bạn chọn lọc cẩn thận những thay đổi nào sẽ được gộp vào một commit, thay vì phải commit tất cả mọi thay đổi trong Working Directory.

3.  **Git Directory (Thư mục .git / Repository cục bộ):**
    - Đây là nơi Git lưu trữ tất cả siêu dữ liệu và cơ sở dữ liệu đối tượng cho dự án của bạn – chính là Local Repository của bạn.
    - Khi bạn thực hiện lệnh `git commit`, Git sẽ lấy những thay đổi đã được "stage" trong Staging Area, tạo một snapshot mới, và lưu trữ snapshot đó vĩnh viễn vào Git Directory (Local Repository).
    - Thư mục `.git` chứa tất cả các commit, các nhánh, các tag, log, cấu hình... Mọi thứ Git cần để quản lý dự án của bạn.

**Luồng làm việc cơ bản:**
Bạn sẽ lặp đi lặp lại chu trình sau:

1.  **Modify:** Chỉnh sửa các file trong **Working Directory**.
2.  **Stage:** Chọn lọc những thay đổi bạn muốn đưa vào commit tiếp theo bằng cách đưa chúng vào **Staging Area** (sử dụng `git add`).
3.  **Commit:** Lưu trữ snapshot của Staging Area vào **Git Directory** (Local Repository) (sử dụng `git commit`).

#### 2.3. Commit

- Một **Commit** là một bản ghi (snapshot) các thay đổi của dự án tại một thời điểm cụ thể, được lưu trữ an toàn trong Local Repository.
- Mỗi commit có một **mã định danh duy nhất (SHA-1 hash)**, ví dụ: `a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b0`.
- Mỗi commit cũng chứa thông tin về **tác giả (author)**, **người commit (committer)**, **ngày giờ commit**, và một **thông điệp commit (commit message)** mô tả những thay đổi trong commit đó.
- **Commit message rất quan trọng!** Nó giúp bạn và những người khác hiểu được mục đích của commit đó khi xem lại lịch sử.
- Việc commit thường xuyên với những thay đổi nhỏ và commit message rõ ràng là một thói quen tốt.

#### 2.4. Branch (Nhánh)

- **Branch (Nhánh)** trong Git là một con trỏ di động trỏ đến một commit cụ thể. Nó đại diện cho một dòng phát triển độc lập.
- Khi bạn tạo một repository mới, Git sẽ tự động tạo một nhánh mặc định tên là `main` (hoặc `master` trong các phiên bản Git cũ hơn).
- **Lợi ích của Branching:**
  - **Phát triển song song:** Nhiều người có thể làm việc trên các tính năng khác nhau cùng lúc trên các nhánh riêng biệt.
  - **Thử nghiệm an toàn:** Bạn có thể tạo một nhánh mới để thử nghiệm một ý tưởng hoặc sửa một lỗi phức tạp mà không làm ảnh hưởng đến code ổn định trên nhánh `main`.
  - **Tổ chức code:** Giúp quản lý các phiên bản khác nhau của dự án (ví dụ: nhánh cho phiên bản phát triển, nhánh cho phiên bản đã phát hành).
- Các thao tác phổ biến với nhánh: tạo nhánh (`git branch <ten_nhanh>`), chuyển nhánh (`git checkout <ten_nhanh>` hoặc `git switch <ten_nhanh>`), xóa nhánh, gộp nhánh.

#### 2.5. Merge (Gộp nhánh)

- **Merge (Gộp nhánh)** là hành động tích hợp các thay đổi từ một nhánh này vào một nhánh khác.
- Ví dụ, sau khi bạn hoàn thành việc phát triển một tính năng mới trên nhánh `feature-X`, bạn sẽ muốn gộp (merge) những thay đổi đó từ nhánh `feature-X` vào nhánh `main`.
- Git cố gắng tự động gộp các thay đổi. Tuy nhiên, nếu có những thay đổi xung đột (ví dụ: cùng một dòng code được sửa đổi khác nhau trên cả hai nhánh), Git sẽ dừng lại và yêu cầu bạn **giải quyết xung đột (resolve conflicts)** thủ công.
- Có hai kiểu merge chính:
  - **Fast-forward merge:** Xảy ra khi nhánh đích không có commit nào mới kể từ khi nhánh nguồn được tạo ra. Git chỉ đơn giản là di chuyển con trỏ của nhánh đích lên commit mới nhất của nhánh nguồn.
  - **Three-way merge (Merge 3 chiều):** Xảy ra khi cả nhánh đích và nhánh nguồn đều có những commit mới. Git sẽ tìm commit chung gần nhất của cả hai nhánh, sau đó tạo một **commit gộp (merge commit)** mới để kết hợp các thay đổi.

#### 2.6. HEAD

- **HEAD** là một con trỏ đặc biệt trong Git, nó trỏ đến **commit hiện tại** mà bạn đang làm việc trên đó trong Working Directory.
- Thông thường, HEAD trỏ đến commit mới nhất của nhánh hiện tại. Ví dụ, nếu bạn đang ở trên nhánh `main`, HEAD sẽ trỏ đến commit cuối cùng của nhánh `main`.
- Khi bạn `git checkout` một nhánh khác, HEAD sẽ di chuyển để trỏ đến commit cuối cùng của nhánh đó.
- Khi bạn tạo một commit mới, HEAD (cùng với con trỏ của nhánh hiện tại) sẽ di chuyển lên commit mới đó.
- Bạn cũng có thể `checkout` một commit cụ thể (detached HEAD state), nhưng đây là tình huống nâng cao hơn.

#### 2.7. Tag (Thẻ)

- **Tag (Thẻ)** được sử dụng để đánh dấu một commit cụ thể nào đó là quan trọng, thường là để đánh dấu các phiên bản phát hành (release versions) của dự án (ví dụ: `v1.0`, `v2.1.3`).
- Tag giống như một "bookmark" cố định cho một commit, không di chuyển như branch.
- Có hai loại tag chính:
  - **Lightweight tag (Tag nhẹ):** Chỉ là một con trỏ đến một commit, không lưu thêm thông tin gì khác.
  - **Annotated tag (Tag có chú thích):** Được lưu trữ như một đối tượng đầy đủ trong cơ sở dữ liệu Git. Nó chứa thông tin người tạo tag, ngày tạo, thông điệp tag, và có thể được ký GPG. Nên ưu tiên sử dụng annotated tag cho các bản release chính thức.

#### 2.8. Log (Lịch sử)

- Lệnh `git log` được sử dụng để **xem lịch sử các commit** của dự án.
- Nó hiển thị danh sách các commit theo thứ tự thời gian ngược (commit mới nhất ở trên cùng).
- Mỗi mục log thường bao gồm mã SHA-1 của commit, tác giả, ngày giờ, và commit message.
- `git log` có rất nhiều tùy chọn để bạn tùy chỉnh cách hiển thị thông tin, ví dụ:
  - `git log --oneline`: Hiển thị mỗi commit trên một dòng.
  - `git log --graph`: Hiển thị lịch sử commit dưới dạng đồ thị, rất hữu ích khi xem các nhánh và merge.
  - `git log --author="<ten_tac_gia>"`: Lọc commit theo tác giả.
  - `git log <ten_nhanh>`: Xem lịch sử của một nhánh cụ thể.

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Working Directory:** Thư mục chứa các file dự án mà bạn đang chỉnh sửa.
- **Staging Area (Index):** Nơi lưu các thay đổi đã được chọn để chuẩn bị cho lần commit tiếp theo.
- **Git Directory (.git):** Kho chứa cục bộ, nơi Git lưu trữ tất cả lịch sử và siêu dữ liệu.
- **SHA-1 Hash:** Một chuỗi ký tự duy nhất đại diện cho một commit hoặc đối tượng khác trong Git.
- **Commit Message:** Mô tả đi kèm với mỗi commit, giải thích những gì đã thay đổi.
- **Fast-forward Merge:** Kiểu gộp nhánh đơn giản khi không có thay đổi xung đột và nhánh đích chưa có commit mới.
- **Three-way Merge:** Kiểu gộp nhánh tạo ra một commit gộp mới để kết hợp các thay đổi từ hai nhánh.
- **Merge Conflict:** Xung đột xảy ra khi Git không thể tự động gộp các thay đổi từ các nhánh khác nhau do cùng một phần của file bị sửa đổi khác nhau.
- **Detached HEAD:** Trạng thái khi HEAD trỏ trực tiếp đến một commit cụ thể thay vì một nhánh.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Tại sao Staging Area lại hữu ích? Tại sao không commit trực tiếp từ Working Directory?
- Sự khác biệt chính giữa Branch và Tag là gì? Khi nào bạn sẽ dùng Branch, khi nào dùng Tag?
- Theo bạn, một commit message tốt nên bao gồm những thông tin gì?
- Thử tưởng tượng bạn đang làm việc trên một tính năng mới và đồng nghiệp của bạn cũng đang sửa một lỗi trên cùng các file đó. Điều gì có thể xảy ra khi các bạn cố gắng gộp code?

---

### 📌 Tài liệu & Tham khảo

- Pro Git - Chương 2: Git Basics: [https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)
- Atlassian Git Tutorials - Basic Git Commands: [https://www.atlassian.com/git/tutorials/setting-up-a-repository](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
- Git Terminology: [https://git-scm.com/docs/gitglossary](https://git-scm.com/docs/gitglossary)
- Understanding the Staging Area in Git: [https://www.git-tower.com/learn/git/glossary/staging-area/](https://www.git-tower.com/learn/git/glossary/staging-area/)
