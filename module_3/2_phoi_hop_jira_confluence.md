## 2. Phối hợp Jira với Confluence

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được **lợi ích** của việc tích hợp Jira và Confluence.
- Biết cách **liên kết một Issue từ Jira** sang một trang Confluence và ngược lại.
- Biết cách **nhúng (embed) một danh sách các Issue Jira** (ví dụ: theo bộ lọc) vào trang Confluence.
- Biết cách **tạo nhanh một Issue Jira mới** trực tiếp từ nội dung trên trang Confluence.

---

### 🧩 Nội dung chi tiết

#### 2.1. Tại sao cần tích hợp Jira và Confluence?

Ở Module 2, chúng ta đã học cách dùng Jira để quản lý công việc (Tasks, User Stories, Bugs). Ở phần trước của Module 3, chúng ta đã biết Confluence dùng để quản lý tài liệu (yêu cầu chi tiết, biên bản họp, thiết kế...).

Hai công cụ này phục vụ hai mục đích khác nhau nhưng lại **liên quan mật thiết** trong dự án phần mềm:

- **Công việc (Jira)** thường xuất phát từ **yêu cầu, kế hoạch (Confluence)**.
- **Tài liệu (Confluence)** cần được cập nhật dựa trên **tiến độ công việc (Jira)**.

Nếu sử dụng riêng lẻ, bạn sẽ phải chuyển đổi qua lại giữa hai ứng dụng, copy/paste thông tin, và dễ dẫn đến thiếu sót hoặc thông tin không đồng nhất.

**Tích hợp Jira và Confluence giúp:**

- **Kết nối ngữ cảnh:** Dễ dàng xem tài liệu liên quan đến một công việc và ngược lại.
- **Tiết kiệm thời gian:** Tạo Issue, xem trạng thái Issue ngay trên Confluence mà không cần mở Jira.
- **Tăng tính minh bạch:** Mọi người đều thấy được mối liên hệ giữa kế hoạch/tài liệu và công việc thực thi.
- **Cải thiện cộng tác:** Thảo luận tập trung hơn khi thông tin được liên kết.

Atlassian (công ty tạo ra cả Jira và Confluence) đã xây dựng khả năng tích hợp rất chặt chẽ giữa hai sản phẩm này.

#### 2.2. Liên kết Issue Jira tới trang Confluence (và ngược lại)

Đây là cách phổ biến nhất để kết nối thông tin giữa hai hệ thống.

**Trường hợp 1: Từ Jira liên kết đến Confluence**

- **Khi nào dùng:** Bạn đang xem một User Story hoặc Bug trên Jira và muốn chỉ đến trang tài liệu đặc tả chi tiết hoặc biên bản họp liên quan trên Confluence.
- **Cách làm:**
  1.  Mở Issue trên Jira.
  2.  Trong phần chi tiết Issue, tìm mục **"Linked issues"** hoặc tương tự (giao diện có thể thay đổi đôi chút).
  3.  Nhấn vào **"Link issue"** hoặc biểu tượng liên kết.
  4.  Chọn tab **"Confluence Page"**.
  5.  **Tìm kiếm trang Confluence** bạn muốn liên kết (theo tên trang hoặc dán URL của trang Confluence vào).
  6.  Chọn trang từ kết quả tìm kiếm và nhấn **"Link"**.
  7.  Liên kết sẽ xuất hiện trong mục "Linked issues" của Jira Issue.

_(Hình ảnh minh họa các bước liên kết từ Jira sang Confluence)_

**Trường hợp 2: Từ Confluence liên kết đến Jira**

- **Khi nào dùng:** Bạn đang viết tài liệu trên Confluence (ví dụ: đặc tả yêu cầu) và muốn tham chiếu đến các User Story hoặc Task cụ thể trên Jira đã được tạo cho yêu cầu đó.
- **Cách làm (Dùng Jira Issue Macro):**
  1.  Mở trang Confluence ở chế độ **Edit**.
  2.  Đặt con trỏ vào vị trí muốn chèn liên kết Jira.
  3.  Trên thanh công cụ, nhấn nút **"+" (Insert)** và chọn **"Jira Issue/Filter"** (hoặc gõ `/jira` và chọn).
  4.  Một hộp thoại sẽ hiện ra. Bạn có thể:
      - **Tìm kiếm Issue:** Nhập từ khóa, Issue Key (ví dụ: PROJ-123), hoặc dùng JQL (Jira Query Language - nâng cao).
      - **Recently Viewed:** Chọn từ các Issue bạn xem gần đây.
  5.  Chọn (các) Issue bạn muốn liên kết.
  6.  Nhấn **"Insert"**.
  7.  Liên kết đến Issue Jira sẽ xuất hiện trên trang Confluence, thường hiển thị cả **Issue Key, Summary và Status** hiện tại.
  8.  Nhấn **"Publish"** trang Confluence.

_(Hình ảnh minh họa các bước chèn Jira Issue Macro trên Confluence)_

**Lợi ích:** Khi xem trang Confluence, bạn có thể click trực tiếp vào liên kết để mở Issue trên Jira. Trạng thái của Issue (To Do, In Progress, Done) cũng thường được cập nhật tự động trên trang Confluence.

#### 2.3. Nhúng (Embed) danh sách Issue Jira vào trang Confluence

Thay vì liên kết từng Issue một, bạn có thể hiển thị cả một **danh sách các Issue** từ Jira ngay trên trang Confluence.

- **Khi nào dùng:**
  - Tạo trang tổng hợp tất cả các Bug của dự án.
  - Tạo trang hiển thị các User Story trong một Epic cụ thể.
  - Tạo trang báo cáo tiến độ Sprint, liệt kê các công việc còn lại.
- **Cách làm (Dùng Jira Issue Macro với Bộ lọc/JQL):**
  1.  Mở trang Confluence ở chế độ **Edit**.
  2.  Đặt con trỏ vào vị trí muốn chèn danh sách.
  3.  Nhấn nút **"+" (Insert)** và chọn **"Jira Issue/Filter"** (hoặc gõ `/jira`).
  4.  Trong hộp thoại hiện ra, thay vì tìm kiếm Issue đơn lẻ, bạn chuyển sang tab **"Search"** hoặc nhập trực tiếp **JQL (Jira Query Language)**.
      - **JQL đơn giản:**
        - `project = "PROJ"` (Tất cả Issue của dự án PROJ)
        - `project = "PROJ" AND issuetype = Bug AND status = Open` (Các Bug còn mở của dự án PROJ)
        - `assignee = currentUser() AND status != Done` (Các Issue được gán cho tôi và chưa xong)
        - `fixVersion = "Release 1.0"` (Các Issue thuộc phiên bản Release 1.0)
      - Bạn cũng có thể **lưu một bộ lọc (Filter)** trên Jira trước, rồi chọn bộ lọc đó trong Confluence.
  5.  Sau khi nhập JQL hoặc chọn Filter, nhấn **"Search"**. Kết quả danh sách Issue sẽ hiện ra.
  6.  (Tùy chọn) Nhấn **"Display options"** để chọn các cột thông tin muốn hiển thị (Assignee, Priority, Due Date...).
  7.  Nhấn **"Insert"**.
  8.  Một bảng liệt kê các Issue Jira khớp với bộ lọc sẽ được nhúng vào trang Confluence.
  9.  Nhấn **"Publish"**.

_(Hình ảnh minh họa các bước nhúng danh sách Issue bằng JQL)_

**Lợi ích:** Danh sách này sẽ **tự động cập nhật** khi có thay đổi trên Jira (ví dụ: thêm Issue mới, thay đổi trạng thái). Giúp tạo các trang báo cáo, tổng hợp động rất hiệu quả.

#### 2.4. Tạo Issue Jira trực tiếp từ Confluence

Đôi khi, trong lúc viết tài liệu hoặc đọc góp ý trên Confluence, bạn nhận ra cần phải tạo một công việc mới trên Jira (ví dụ: một Task để sửa tài liệu, một Bug vừa phát hiện).

- **Cách làm 1: Tạo Issue từ văn bản bôi đen**
  1.  Trên trang Confluence (chế độ View hoặc Edit), **bôi đen đoạn văn bản** bạn muốn dùng làm tiêu đề (Summary) hoặc mô tả (Description) cho Issue mới.
  2.  Một menu nhỏ sẽ xuất hiện, chọn **"Create Jira issue"**.
  3.  Một hộp thoại tạo Issue nhanh sẽ hiện ra:
      - Chọn **Project** và **Issue Type** (Task, Bug, Story...).
      - **Summary** thường được điền sẵn từ văn bản bạn bôi đen.
      - Bạn có thể thêm **Description** hoặc chỉnh sửa các trường khác.
  4.  Nhấn **"Create"**.
  5.  Issue mới sẽ được tạo trên Jira, và một liên kết đến Issue đó sẽ tự động được chèn vào vị trí bạn bôi đen trên trang Confluence.

_(Hình ảnh minh họa tạo Issue từ văn bản bôi đen)_

- **Cách làm 2: Dùng nút "Create Jira issue" trong trình soạn thảo**
  1.  Mở trang Confluence ở chế độ **Edit**.
  2.  Đặt con trỏ vào vị trí muốn tạo liên kết đến Issue mới.
  3.  Trên thanh công cụ, nhấn **"+" (Insert)** và chọn **"Jira Issue/Filter"** (hoặc gõ `/jira`).
  4.  Trong hộp thoại, chọn tab **"Create new issue"**.
  5.  Điền thông tin: **Project, Issue Type, Summary, Description...**
  6.  Nhấn **"Insert"**.
  7.  Issue mới sẽ được tạo trên Jira và liên kết được chèn vào trang Confluence.

**Lợi ích:** Giúp luồng công việc liền mạch, không cần chuyển sang Jira chỉ để tạo một Issue đơn giản liên quan đến nội dung đang xem/viết trên Confluence.

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Integration (Tích hợp):** Việc kết nối hai hoặc nhiều hệ thống/ứng dụng khác nhau để chúng có thể trao đổi dữ liệu và hoạt động cùng nhau một cách liền mạch.
- **Embed (Nhúng):** Chèn nội dung từ một nguồn (ví dụ: danh sách Issue Jira) vào một trang của nguồn khác (ví dụ: trang Confluence) sao cho nội dung đó hiển thị trực tiếp.
- **Macro (Confluence Macro):** Một tính năng nhỏ trong Confluence cho phép bạn thêm các nội dung động hoặc định dạng phức tạp vào trang (ví dụ: Jira Issue Macro, Table of Contents Macro...).
- **JQL (Jira Query Language):** Ngôn ngữ truy vấn mạnh mẽ của Jira, cho phép bạn tìm kiếm Issue dựa trên nhiều tiêu chí khác nhau (project, issuetype, status, assignee...). Rất hữu ích khi tạo bộ lọc hoặc nhúng danh sách Issue vào Confluence.
- **Filter (Bộ lọc - Jira):** Một truy vấn JQL đã được lưu lại trên Jira để có thể tái sử dụng nhanh chóng.

---

### 🎯 Ví dụ thực tế: Quy trình làm việc tích hợp

1.  **Product Owner viết Đặc tả Yêu cầu** cho tính năng "Thanh toán Online" trên **Confluence**.
2.  Trong trang đặc tả, PO **bôi đen** từng yêu cầu nhỏ và **tạo các User Story tương ứng trên Jira** trực tiếp từ Confluence. Các liên kết Jira Story tự động chèn vào trang đặc tả.
3.  **Nhóm phát triển họp Sprint Planning**. Họ mở trang đặc tả trên Confluence, xem các User Story đã liên kết (thấy cả trạng thái "To Do").
4.  Nhóm quyết định chọn 3 User Story cho Sprint 1. Họ cập nhật trạng thái các Story này trên Jira (hoặc trực tiếp từ Confluence nếu Macro cho phép).
5.  **Scrum Master tạo một trang "Sprint 1 Dashboard"** trên Confluence.
6.  Trên trang Dashboard, SM **nhúng một danh sách Issue Jira** dùng JQL: `project = "PROJ" AND sprint = "Sprint 1"` để hiển thị tất cả công việc của Sprint 1.
7.  Trong quá trình Sprint, **Tester tìm thấy lỗi** khi kiểm thử tính năng. Tester vào trang đặc tả trên Confluence, **bôi đen** mô tả lỗi và **tạo Bug trên Jira**. Liên kết Bug tự động thêm vào Confluence.
8.  Cuối Sprint, mọi người xem trang "Sprint 1 Dashboard" trên Confluence để thấy nhanh các công việc đã "Done" và còn lại.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Bạn thấy tính năng tích hợp nào giữa Jira và Confluence là hữu ích nhất cho người mới bắt đầu? Tại sao?
- Khi nào bạn nên liên kết từng Issue một, khi nào nên nhúng cả danh sách Issue?
- Việc tạo Issue Jira trực tiếp từ Confluence có thể gây ra vấn đề gì nếu không cẩn thận? (Ví dụ: tạo trùng lặp, thiếu thông tin).

---

### 📌 Tài liệu & Tham khảo

- **Use Jira and Confluence together:** [https://support.atlassian.com/confluence-cloud/docs/use-jira-and-confluence-together/](https://support.atlassian.com/confluence-cloud/docs/use-jira-and-confluence-together/)
- **Insert the Jira Issues macro:** [https://support.atlassian.com/confluence-cloud/docs/insert-the-jira-issues-macro/](https://support.atlassian.com/confluence-cloud/docs/insert-the-jira-issues-macro/)
- **Create Jira issues from Confluence:** [https://support.atlassian.com/confluence-cloud/docs/create-jira-issues-from-confluence/](https://support.atlassian.com/confluence-cloud/docs/create-jira-issues-from-confluence/)
- **Search for Jira issues using JQL:** [https://support.atlassian.com/jira-software-cloud/docs/search-for-jira-issues-using-jql/](https://support.atlassian.com/jira-software-cloud/docs/search-for-jira-issues-using-jql/)
