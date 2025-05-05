## 3. Tích hợp với các công cụ khác

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Biết cách **chia sẻ nhanh chóng nội dung Confluence** qua các công cụ chat như Telegram.
- Hiểu khái niệm về việc **nhúng nội dung từ các công cụ khác** (ví dụ: FigJam) vào Confluence.
- Nhận biết **Google Drive như một giải pháp thay thế/bổ sung** cho Confluence và cách liên kết giữa chúng.
- Hiểu được tầm quan trọng của việc lựa chọn công cụ phù hợp cho từng loại thông tin và ngữ cảnh giao tiếp.

---

### 🧩 Nội dung chi tiết

Confluence là một công cụ mạnh mẽ để quản lý tài liệu và kiến thức, nhưng trong hệ sinh thái làm việc của một đội nhóm (đặc biệt là đội nhóm từ xa), nó thường không đứng một mình. Việc tích hợp Confluence với các công cụ giao tiếp và cộng tác khác giúp luồng thông tin trở nên liền mạch và hiệu quả hơn.

#### 3.1. Chia sẻ và Thảo luận nội dung Confluence qua Telegram (hoặc công cụ chat khác)

Đôi khi, bạn cần thảo luận nhanh về một tài liệu hoặc thông báo cho nhóm về một cập nhật quan trọng trên Confluence. Thay vì yêu cầu mọi người tự vào Confluence tìm trang, bạn có thể chủ động chia sẻ liên kết.

- **Khi nào dùng:**
  - Thông báo cho nhóm về một biên bản họp vừa được đăng.
  - Hỏi nhanh ý kiến về một phần cụ thể trong tài liệu đặc tả.
  - Chia sẻ một hướng dẫn kỹ thuật mới cho thành viên mới.
- **Cách làm:**
  1.  Mở trang Confluence bạn muốn chia sẻ.
  2.  Trên thanh địa chỉ của trình duyệt, **copy URL (đường link)** của trang đó.
  3.  Mở ứng dụng **Telegram** (hoặc Slack, Zalo...).
  4.  Vào **nhóm chat** của dự án hoặc chat riêng với người cần gửi.
  5.  **Dán (paste) URL** vào ô soạn tin nhắn.
  6.  **(Quan trọng)** Thêm một **tin nhắn mô tả ngắn gọn** về nội dung bạn đang chia sẻ và **lý do** bạn muốn mọi người xem (ví dụ: "Biên bản họp Sprint Planning hôm nay đã có trên Confluence nhé mọi người:", "Nhờ @Tester xem giúp phần yêu cầu A.1 trong đặc tả này:", "Hướng dẫn cài đặt môi trường cho thành viên mới:").
  7.  Gửi tin nhắn.

_(Hình ảnh minh họa tin nhắn Telegram có chứa link Confluence và mô tả)_

- **Lợi ích:**
  - **Nhanh chóng và tiện lợi:** Mọi người nhận được thông báo ngay trên công cụ chat quen thuộc.
  - **Tăng khả năng tiếp cận:** Giúp những người ít khi chủ động vào Confluence vẫn nắm được thông tin.
  - **Tạo điểm bắt đầu thảo luận:** Cuộc thảo luận nhanh có thể diễn ra ngay trên Telegram, sau đó kết luận quan trọng có thể được cập nhật lại vào trang Confluence.
- **Lưu ý:**
  - **Không lạm dụng:** Tránh spam nhóm chat bằng quá nhiều link Confluence không cần thiết.
  - **Cung cấp ngữ cảnh:** Luôn giải thích tại sao bạn chia sẻ link đó.
  - **Đảm bảo quyền truy cập:** Người nhận link cần có quyền xem trang Confluence đó.

#### 3.2. Nhúng nội dung từ công cụ khác vào Confluence

Confluence cho phép bạn "nhúng" (embed) nội dung từ nhiều ứng dụng web phổ biến khác vào trang tài liệu của mình. Điều này giúp tập trung thông tin từ nhiều nguồn vào một chỗ.

- **Ví dụ các công cụ có thể nhúng:**
  - **FigJam/Figma:** Nhúng trực tiếp bảng trắng brainstorm hoặc thiết kế giao diện.
  - **Google Drive (Docs, Sheets, Slides):** Hiển thị nội dung tài liệu Google ngay trên trang Confluence.
  - **YouTube/Vimeo:** Nhúng video hướng dẫn hoặc demo.
  - **Microsoft OneDrive/SharePoint:** Nhúng tài liệu Office.
  - **Trello:** Nhúng board Trello.
  - ... và nhiều ứng dụng khác thông qua các "Macro" hoặc tính năng "Smart Link" của Atlassian.
- **Cách làm (Ví dụ với FigJam):**
  1.  Mở **bảng FigJam** bạn muốn nhúng.
  2.  Tìm nút **"Share"** (Chia sẻ).
  3.  Chọn tùy chọn để **lấy link chia sẻ công khai** (public link) hoặc link cho phép nhúng (embed link). Đảm bảo quyền xem phù hợp.
  4.  **Copy link** đó.
  5.  Mở trang **Confluence** ở chế độ **Edit**.
  6.  **Dán (paste) link FigJam** vừa copy vào trình soạn thảo.
  7.  Confluence thường sẽ tự động nhận diện link và **hiển thị bản xem trước (preview)** của bảng FigJam. Bạn có thể chọn cách hiển thị (link đơn giản, thẻ xem trước nhỏ, hoặc nhúng toàn bộ bảng - inline embed).
  8.  Chọn **"Inline embed"** hoặc tương tự để bảng FigJam hiển thị trực tiếp trên trang.
  9.  Nhấn **"Publish"**.

_(Hình ảnh minh họa nhúng bảng FigJam vào Confluence)_

- **Lợi ích:**
  - **Tập trung thông tin:** Người đọc không cần rời khỏi Confluence để xem nội dung từ các công cụ khác.
  - **Trực quan hóa:** Hiển thị sơ đồ, thiết kế, video ngay trong ngữ cảnh của tài liệu.
  - **Luôn cập nhật:** Nội dung nhúng thường tự động cập nhật khi có thay đổi ở nguồn gốc (ví dụ: sửa bảng FigJam thì nội dung nhúng trên Confluence cũng thay đổi theo).
- **Lưu ý:**
  - **Quyền truy cập:** Người xem trang Confluence cũng cần có quyền truy cập vào nội dung gốc được nhúng (ví dụ: quyền xem bảng FigJam).
  - **Hiệu suất:** Nhúng quá nhiều nội dung phức tạp có thể làm trang Confluence tải chậm hơn.

#### 3.3. Sử dụng Google Drive như một giải pháp thay thế/bổ sung

Mặc dù Confluence rất mạnh mẽ cho việc tạo và quản lý tài liệu có cấu trúc (wiki-style), nhưng đôi khi **Google Drive** (bao gồm Google Docs, Sheets, Slides) vẫn có những ưu điểm riêng và thường được sử dụng song song:

- **Khi nào Google Drive có thể phù hợp hơn:**
  - **Soạn thảo văn bản/bảng tính phức tạp:** Google Docs/Sheets có nhiều tính năng định dạng và công thức mạnh mẽ hơn trình soạn thảo cơ bản của Confluence.
  - **Lưu trữ các loại file đa dạng:** Drive dễ dàng lưu trữ mọi định dạng file (PDF, ảnh, video, file nén...) mà không cần tạo "trang" như Confluence.
  - **Cộng tác thời gian thực quen thuộc:** Nhiều người đã quen với việc cùng nhau chỉnh sửa Google Docs/Sheets trong thời gian thực.
  - **Chia sẻ với người ngoài tổ chức:** Việc chia sẻ file/thư mục trên Google Drive với đối tác hoặc khách hàng bên ngoài đôi khi đơn giản hơn Confluence (tùy cấu hình).
  - **Chi phí:** Google Drive thường có gói miễn phí dung lượng lớn.
- **Cách kết hợp Confluence và Google Drive:**
  - **Lưu file lớn trên Drive, link từ Confluence:** Thay vì upload file lớn (video, file cài đặt...) trực tiếp lên Confluence (có thể tốn dung lượng), hãy upload lên Google Drive, lấy link chia sẻ và dán link đó vào trang Confluence liên quan.
  - **Nhúng tài liệu Google Drive vào Confluence:** Sử dụng tính năng nhúng (tương tự như nhúng FigJam) để hiển thị nội dung Google Docs/Sheets/Slides trực tiếp trên trang Confluence. Atlassian cung cấp Macro "Google Drive for Confluence" để làm việc này.
  - **Quy ước rõ ràng:** Đội nhóm cần thống nhất khi nào dùng Confluence, khi nào dùng Google Drive để tránh thông tin bị phân mảnh. Ví dụ:
    - **Confluence:** Dùng cho các tài liệu chính thức, có cấu trúc, cần thảo luận và liên kết Jira (đặc tả yêu cầu, biên bản họp, kiến trúc hệ thống, hướng dẫn quy trình).
    - **Google Drive:** Dùng cho các file nháp, bảng tính phức tạp, lưu trữ file media, tài liệu cần chia sẻ rộng rãi ra bên ngoài, hoặc các tài liệu mang tính cá nhân hơn.

_(Hình ảnh minh họa nhúng Google Doc vào Confluence)_

- **Lợi ích của việc kết hợp:** Tận dụng điểm mạnh của cả hai công cụ, lựa chọn công cụ phù hợp nhất cho từng loại thông tin cụ thể.
- **Thách thức:** Cần có quy tắc rõ ràng để tránh nhầm lẫn và đảm bảo mọi người biết tìm thông tin ở đâu.

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **URL (Uniform Resource Locator):** Địa chỉ duy nhất của một tài nguyên trên web (ví dụ: một trang Confluence, một file Google Drive).
- **Paste (Dán):** Hành động chèn nội dung đã được sao chép (copy) vào một vị trí khác.
- **Spam:** Gửi hàng loạt tin nhắn hoặc thông tin không mong muốn, gây phiền nhiễu.
- **Inline Embed:** Hiển thị nội dung được nhúng trực tiếp bên trong trang, thay vì chỉ là một liên kết hoặc một thẻ xem trước nhỏ.
- **Smart Link (Atlassian):** Tính năng tự động nhận diện các link từ các dịch vụ phổ biến (Jira, Google Drive, Figma...) và hiển thị chúng dưới dạng thẻ xem trước hoặc nội dung nhúng.
- **Wiki-style:** Phong cách tài liệu giống như các trang wiki, nơi nội dung được tổ chức thành các trang liên kết với nhau, dễ dàng chỉnh sửa và điều hướng.
- **Media Files:** Các tệp đa phương tiện như hình ảnh, âm thanh, video.

---

### 🎯 Ví dụ thực tế: Kết hợp công cụ

- **Kịch bản:** Nhóm đang chuẩn bị cho buổi Sprint Review.
- **Hành động:**
  1.  **Scrum Master** tạo một trang **"Chuẩn bị Sprint Review - Sprint 3"** trên **Confluence**.
  2.  Trong trang Confluence, SM **nhúng danh sách các User Story đã hoàn thành** trong Sprint 3 từ **Jira** (dùng Jira Issue Macro).
  3.  SM **nhúng bảng FigJam** chứa kết quả brainstorm từ buổi Retrospective Sprint 2 (dùng link FigJam).
  4.  **Designer** lưu các file thiết kế giao diện cuối cùng (định dạng .fig hoặc .png) lên một thư mục trên **Google Drive**. Designer lấy link chia sẻ thư mục đó và **dán link vào trang Confluence**.
  5.  **Product Owner** soạn thảo slide trình bày kết quả Sprint trên **Google Slides**. PO lấy link chia sẻ slide và **nhúng slide đó vào trang Confluence**.
  6.  Cuối cùng, SM **copy link trang Confluence** tổng hợp này và gửi vào **nhóm chat Telegram** với lời nhắn: "Tài liệu chuẩn bị cho Sprint Review chiều nay đã sẵn sàng trên Confluence, mọi người xem qua nhé!".

Kết quả: Mọi thông tin cần thiết cho buổi họp từ nhiều nguồn khác nhau đều được tập trung tại một trang Confluence duy nhất, dễ dàng truy cập và tham chiếu.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Ngoài Telegram, FigJam, Google Drive, bạn biết công cụ nào khác có thể tích hợp tốt với Confluence không?
- Theo bạn, quy tắc nào là quan trọng nhất khi quyết định nên lưu trữ thông tin trên Confluence hay Google Drive?
- Việc nhúng quá nhiều nội dung từ bên ngoài vào Confluence có thể gây ra rủi ro gì về bảo mật hoặc quản lý quyền truy cập?

---

### 📌 Tài liệu & Tham khảo

- **Share Confluence pages and blog posts:** [https://support.atlassian.com/confluence-cloud/docs/share-confluence-pages-and-blog-posts/](https://support.atlassian.com/confluence-cloud/docs/share-confluence-pages-and-blog-posts/)
- **Display files and images:** (Đề cập đến việc nhúng từ các nguồn khác nhau) [https://support.atlassian.com/confluence-cloud/docs/display-files-and-images/](https://support.atlassian.com/confluence-cloud/docs/display-files-and-images/)
- **Use the FigJam for Confluence macro:** [https://support.atlassian.com/confluence-cloud/docs/use-the-figjam-for-confluence-macro/](https://support.atlassian.com/confluence-cloud/docs/use-the-figjam-for-confluence-macro/)
- **Use the Google Drive & Docs for Confluence macro:** [https://support.atlassian.com/confluence-cloud/docs/use-the-google-drive-docs-for-confluence-macro/](https://support.atlassian.com/confluence-cloud/docs/use-the-google-drive-docs-for-confluence-macro/)
- **Smart Links:** [https://support.atlassian.com/confluence-cloud/docs/insert-links-and-anchors/#Smart-Links](https://support.atlassian.com/confluence-cloud/docs/insert-links-and-anchors/#Smart-Links)
