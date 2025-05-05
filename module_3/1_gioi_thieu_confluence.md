## 1. Giới thiệu Confluence

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được **vai trò của Confluence** như một nơi lưu trữ tài liệu tập trung cho dự án phần mềm.
- Nhận biết các thành phần giao diện cơ bản: **Spaces, Pages, Dashboard**.
- Biết cách **tạo và chỉnh sửa một trang tài liệu** đơn giản bằng trình soạn thảo của Confluence.
- Hiểu cách **tổ chức nội dung** bằng Spaces và cấu trúc cây thư mục (Page Tree).
- Biết cách sử dụng các tính năng **cộng tác cơ bản** như comment và @mention.

---

### 🧩 Nội dung chi tiết

#### 1.1. Tại sao cần Confluence? Vai trò trong dự án

Hãy tưởng tượng dự án của bạn có rất nhiều thông tin cần lưu trữ:

- Yêu cầu của khách hàng (User Stories, đặc tả chi tiết).
- Biên bản các cuộc họp quan trọng (Sprint Planning, Review...).
- Tài liệu hướng dẫn kỹ thuật, thiết kế hệ thống.
- Kế hoạch dự án, báo cáo tiến độ.
- Các ghi chú, ý tưởng, kết quả nghiên cứu...

Nếu những thông tin này nằm rải rác ở email, file Word/Excel trên máy cá nhân, tin nhắn chat... thì sẽ rất khó để:

- **Tìm kiếm lại** khi cần.
- **Đảm bảo mọi người** (kể cả thành viên mới) đều có thông tin cập nhật nhất.
- **Cùng nhau đóng góp**, chỉnh sửa và thảo luận trên tài liệu.

**Confluence ra đời để giải quyết vấn đề này!**

Nó giống như một **trang web nội bộ (wiki)** hoặc một **cơ sở tri thức (knowledge base)** dành riêng cho đội nhóm hoặc tổ chức của bạn.

**Vai trò chính của Confluence:**

- **Lưu trữ tập trung:** Mọi tài liệu quan trọng của dự án đều nằm ở một nơi duy nhất.
- **Dễ dàng truy cập:** Ai cũng có thể tìm kiếm và đọc tài liệu (nếu được cấp quyền).
- **Cộng tác hiệu quả:** Nhiều người có thể cùng xem, sửa đổi, và bình luận trên cùng một trang tài liệu.
- **Tổ chức khoa học:** Sắp xếp tài liệu theo từng dự án, chủ đề một cách logic.
- **Tích hợp tốt:** Kết nối dễ dàng với Jira và các công cụ khác.

Trong bối cảnh làm việc từ xa, vai trò của một nơi lưu trữ tài liệu tập trung như Confluence càng trở nên quan trọng hơn bao giờ hết.

#### 1.2. Giao diện cơ bản

Khi bạn truy cập Confluence (thường là phiên bản Cloud tại `your-domain.atlassian.net/wiki`), bạn sẽ thấy một số thành phần chính:

- **Dashboard (Bảng tin):**
  - Trang đầu tiên bạn thấy khi đăng nhập.
  - Hiển thị các cập nhật mới nhất từ các Space bạn theo dõi, các trang bạn đã xem gần đây, hoặc các thông báo quan trọng.
  - Giúp bạn nhanh chóng nắm bắt những gì đang diễn ra.
- **Spaces (Không gian):**
  - Giống như các **thư mục lớn** để chứa tài liệu cho một **đội nhóm, dự án, hoặc chủ đề cụ thể**.
  - Ví dụ: Space "Marketing Team", Space "Dự án Website Khóa học", Space "Hướng dẫn Nhân viên Mới".
  - Mỗi Space có thể có quyền truy cập riêng.
- **Pages (Trang):**
  - Là **đơn vị nội dung cơ bản** trong Confluence, giống như một trang tài liệu Word hoặc một bài viết blog.
  - Nơi bạn viết yêu cầu, biên bản họp, hướng dẫn...
  - Các trang được tổ chức bên trong các Space.

_(Hình ảnh minh họa giao diện Dashboard và danh sách Spaces)_

#### 1.3. Tạo và Chỉnh sửa Trang (Page)

Việc tạo và sửa trang trên Confluence rất trực quan, giống như sử dụng Google Docs hay Microsoft Word online.

**Các bước tạo trang mới:**

1.  Đi đến **Space** mà bạn muốn tạo trang.
2.  Nhấn nút **"Create"** (Thường ở góc trên bên phải).
3.  Confluence sẽ mở ra một trang trắng với **trình soạn thảo (editor)**.

**Trình soạn thảo Confluence:**

- **Giao diện WYSIWYG (What You See Is What You Get):** Bạn thấy gì trên màn hình soạn thảo thì khi xuất bản trang sẽ trông y như vậy.
- **Thanh công cụ định dạng:** Cung cấp các nút để:
  - **Định dạng văn bản:** In đậm, in nghiêng, gạch chân, tiêu đề (Heading 1, 2, 3...), danh sách (bullet, đánh số).
  - **Chèn nội dung:** Bảng (table), hình ảnh, link, file đính kèm, biểu tượng cảm xúc (emoji), code block...
  - **Layout:** Chia cột cho trang.
  - **Macros:** Các tính năng nâng cao như tạo mục lục tự động, nhúng nội dung từ Jira, vẽ sơ đồ... (Sẽ tìm hiểu thêm sau).
- **Lưu và Xuất bản:**
  - Confluence tự động lưu nháp (draft) khi bạn đang gõ.
  - Nhấn **"Publish"** để đăng trang cho mọi người trong Space thấy.
  - Bạn cũng có thể xem trước (Preview) hoặc hủy bỏ (Close).

_(Hình ảnh minh họa trình soạn thảo và thanh công cụ)_

**Chỉnh sửa trang đã có:**

1.  Mở trang bạn muốn sửa.
2.  Nhấn nút **"Edit"** (biểu tượng bút chì).
3.  Thực hiện thay đổi trong trình soạn thảo.
4.  Nhấn **"Publish"** để lưu lại thay đổi. Confluence sẽ lưu lại lịch sử các phiên bản chỉnh sửa.

#### 1.4. Tổ chức nội dung: Spaces và Page Trees

Để tài liệu không bị lộn xộn, Confluence cung cấp hai cấp độ tổ chức chính:

- **Spaces:** Như đã nói, đây là cấp độ cao nhất, phân chia tài liệu theo nhóm, dự án hoặc mục đích lớn. Việc tạo Space thường do quản trị viên hoặc người được cấp quyền thực hiện.
- **Page Tree (Cây thư mục trang):**
  - Bên trong mỗi Space, các trang được tổ chức theo cấu trúc **cha-con**, giống như cây thư mục trên máy tính.
  - Một trang có thể là "con" của một trang khác.
  - Ví dụ:
    ```
    Space: Dự án Website Khóa học
    └── Trang chủ Dự án (Parent Page)
        ├── Yêu cầu Chức năng (Child Page)
        │   ├── Trang Đăng nhập (Grandchild Page)
        │   └── Trang Danh sách Khóa học (Grandchild Page)
        ├── Thiết kế Giao diện (Child Page)
        └── Biên bản Họp (Child Page)
            ├── Họp Kick-off 10/05 (Grandchild Page)
            └── Họp Sprint 1 Planning 17/05 (Grandchild Page)
    ```
  - Cấu trúc này giúp người đọc dễ dàng điều hướng và hiểu mối quan hệ giữa các tài liệu.
  - Bạn có thể dễ dàng kéo thả các trang trong cây thư mục (ở thanh bên trái) để sắp xếp lại.

_(Hình ảnh minh họa cấu trúc Page Tree)_

#### 1.5. Cộng tác trên trang: Comment và @mention

Confluence không chỉ để lưu trữ mà còn là nơi để **thảo luận và cộng tác** trực tiếp trên nội dung.

- **Comments (Bình luận):**
  - Bạn có thể để lại bình luận ở **cuối mỗi trang** để thảo luận chung về nội dung trang đó.
  - Bạn cũng có thể **bôi đen một đoạn văn bản cụ thể** và chọn **"Comment"** để bình luận chính xác vào phần đó (inline comment). Điều này rất hữu ích khi góp ý, đặt câu hỏi về một chi tiết cụ thể.
- **@mention:**
  - Khi viết bình luận hoặc soạn thảo trang, bạn có thể gõ `@` theo sau là tên của một người dùng Confluence khác (ví dụ: `@John Doe`).
  - Người được nhắc đến (@mention) sẽ nhận được **thông báo** (qua email hoặc trong Confluence) về bình luận hoặc trang đó.
  - Đây là cách hiệu quả để thu hút sự chú ý của ai đó vào một vấn đề cụ thể hoặc giao việc.

_(Hình ảnh minh họa cách thêm comment và @mention)_

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Wiki:** Một loại website cho phép người dùng dễ dàng tạo, sửa đổi và liên kết các trang nội dung với nhau. Wikipedia là ví dụ nổi tiếng nhất. Confluence hoạt động dựa trên nguyên tắc tương tự.
- **Knowledge Base (Cơ sở tri thức):** Một kho lưu trữ tập trung thông tin, tài liệu, hướng dẫn, câu hỏi thường gặp... của một tổ chức hoặc sản phẩm.
- **Dashboard:** Bảng điều khiển tổng quan, thường hiển thị thông tin tóm tắt và cập nhật quan trọng.
- **Space:** Không gian làm việc riêng biệt trong Confluence, dùng để nhóm các trang liên quan đến một chủ đề, dự án hoặc nhóm cụ thể.
- **Page:** Một trang tài liệu đơn lẻ trong Confluence.
- **Editor (Trình soạn thảo):** Công cụ dùng để tạo và chỉnh sửa nội dung trang.
- **WYSIWYG (What You See Is What You Get):** Giao diện soạn thảo mà những gì bạn thấy trên màn hình chỉnh sửa sẽ giống hệt như kết quả cuối cùng khi xuất bản.
- **Page Tree:** Cấu trúc phân cấp cha-con của các trang trong một Space, giúp tổ chức tài liệu một cách logic.
- **Comment (Bình luận):** Ghi chú, phản hồi hoặc thảo luận được thêm vào một trang hoặc một phần cụ thể của trang.
- **@mention (Nhắc đến):** Cách gọi tên một người dùng khác trong Confluence để thông báo cho họ.

---

### 🎯 Ví dụ thực tế: Tạo trang "Biên bản họp Sprint Planning"

1.  **Vào Space** của dự án.
2.  Nhấn **"Create"**.
3.  **Đặt tiêu đề:** "Biên bản họp Sprint 1 Planning - 05/05/2025".
4.  **Sử dụng định dạng:**
    - Dùng **Heading 2** cho các mục: "Người tham dự", "Mục tiêu Sprint", "Các User Story đã chọn", "Công việc phân công", "Quyết định khác".
    - Dùng **danh sách bullet** để liệt kê người tham dự, user story.
    - Dùng **bảng** để liệt kê công việc phân công (Tên công việc | Người thực hiện | Dự kiến hoàn thành).
5.  **Sử dụng @mention:** Trong phần "Người tham dự" và "Người thực hiện", gõ `@` để tag tên các thành viên.
6.  **Nhấn "Publish"**.
7.  Sau khi publish, vào phần **Comment** ở cuối trang, viết: "Mọi người xem lại và cho ý kiến nhé. `@Scrum Master` xem giúp phần phân công đã hợp lý chưa."

---

### 🧠 Câu hỏi thảo luận gợi mở

- Theo bạn, loại tài liệu nào là quan trọng nhất cần đưa lên Confluence trong một dự án phần mềm?
- So với việc lưu tài liệu trên Google Drive, Confluence có ưu điểm gì hơn trong việc tổ chức và cộng tác?
- Khi nào bạn sẽ dùng comment ở cuối trang, khi nào dùng inline comment?

---

### 📌 Tài liệu & Tham khảo

- **Atlassian Confluence Cloud Documentation:**
  - Get started with Confluence Cloud: [https://support.atlassian.com/confluence-cloud/docs/get-started-with-confluence-cloud/](https://support.atlassian.com/confluence-cloud/docs/get-started-with-confluence-cloud/)
  - Create and edit pages: [https://support.atlassian.com/confluence-cloud/docs/create-and-edit-pages/](https://support.atlassian.com/confluence-cloud/docs/create-and-edit-pages/)
  - Spaces: [https://support.atlassian.com/confluence-cloud/docs/spaces/](https://support.atlassian.com/confluence-cloud/docs/spaces/)
  - Use comments and mentions: [https://support.atlassian.com/confluence-cloud/docs/use-comments-and-mentions/](https://support.atlassian.com/confluence-cloud/docs/use-comments-and-mentions/)
- (Video) Confluence Cloud Beginner Tutorial (Tìm kiếm trên YouTube)
