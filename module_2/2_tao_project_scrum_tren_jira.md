## 2. Tạo Project Scrum trên Jira

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được khái niệm **Project Template** trong Jira và tại sao lại chọn Scrum.
- Nắm được các bước cơ bản để **tạo một Project mới** theo template Scrum trên Jira Cloud.
- Biết cách thực hiện một số **cấu hình cơ bản** cho Project mới (Tên, Khóa, Quyền truy cập).
- Nhận biết và hiểu sơ bộ về các **thành phần chính** trong một Project Scrum: Backlog, Active Sprints, Reports.

---

### 🧩 Nội dung chi tiết

#### 2.1. Project Template là gì? Tại sao chọn Scrum?

Khi bạn bắt đầu một dự án mới trong Jira, nó không bắt đầu từ một trang giấy trắng hoàn toàn. Jira cung cấp các **Project Template (Mẫu Dự án)** được thiết kế sẵn cho các quy trình làm việc phổ biến. Hãy tưởng tượng nó giống như bạn chọn một mẫu CV có sẵn thay vì phải tự kẻ bảng từ đầu.

Một số template phổ biến:

- **Scrum:** Tối ưu cho các nhóm làm việc theo phương pháp Scrum (chia công việc theo các Sprint ngắn, có Backlog, Sprint Planning...). Đây là template rất phổ biến cho phát triển phần mềm.
- **Kanban:** Dành cho các nhóm muốn quản lý luồng công việc liên tục, tập trung vào việc giới hạn công việc đang thực hiện (Work In Progress - WIP). Thường dùng cho các đội hỗ trợ, vận hành hoặc các nhóm không làm việc theo Sprint cố định.
- **Bug Tracking:** Một template đơn giản hơn, tập trung chủ yếu vào việc ghi nhận, theo dõi và sửa lỗi phần mềm.
- **Và nhiều loại khác...**

**Tại sao chúng ta chọn Scrum trong khóa học này?**

- **Phổ biến trong phát triển phần mềm:** Rất nhiều công ty phần mềm áp dụng Scrum hoặc các biến thể của nó. Học cách dùng Jira với template Scrum sẽ giúp bạn dễ dàng hòa nhập vào môi trường làm việc thực tế.
- **Cấu trúc rõ ràng:** Scrum cung cấp một khung làm việc có cấu trúc (Sprint, các buổi lễ như Planning, Review...) giúp nhóm dễ dàng quản lý công việc phức tạp.
- **Hỗ trợ tốt bởi Jira:** Jira có các tính năng được thiết kế riêng để hỗ trợ quy trình Scrum (Backlog, Sprint Board, Burndown Chart...).

#### 2.2. Demo tạo một Project Scrum mới

Việc tạo một Project Scrum mới trên Jira Cloud khá đơn giản. Dưới đây là các bước chính (Giao diện có thể thay đổi đôi chút theo thời gian, nhưng các bước cơ bản là tương tự):

1.  **Đăng nhập vào Jira Cloud:** Sử dụng tài khoản bạn đã tạo ở phần trước.
2.  **Tìm nút tạo Project:** Thường ở thanh điều hướng trên cùng hoặc menu bên trái, tìm mục "Projects" và chọn "Create project".
3.  **Chọn Template:** Jira sẽ hiển thị danh sách các template.
    - Tìm đến nhóm template "Software development".
    - Chọn template **"Scrum"**. Nhấn "Use template".
4.  **Chọn loại Project:** Jira thường hỏi bạn muốn tạo project "Team-managed" hay "Company-managed".
    - **Team-managed:** Đơn giản hơn, dễ cấu hình hơn cho người mới bắt đầu, phù hợp cho các nhóm nhỏ muốn tự quản lý quy trình của mình. **(Nên chọn loại này để bắt đầu)**.
    - **Company-managed:** Mạnh mẽ hơn, nhiều tùy chọn tùy chỉnh hơn, thường được quản lý bởi quản trị viên Jira trong các công ty lớn, chia sẻ cấu hình giữa nhiều dự án.
    - Chọn "Select a Team-managed project".
5.  **Nhập thông tin cơ bản:**
    - **Name (Tên Project):** Đặt tên dễ hiểu cho dự án của bạn (ví dụ: "Học Jira Cơ Bản", "Dự án Website Bán Hàng").
    - **Key (Khóa Project):** Jira sẽ tự động đề xuất một mã khóa ngắn gọn dựa trên tên Project (ví dụ: HJB, DWSBH). Mã này sẽ xuất hiện trong ID của các Issue (ví dụ: HJB-1, HJB-2). Bạn có thể thay đổi nếu muốn, nhưng nên giữ nó ngắn gọn và dễ nhận biết.
6.  **Nhấn nút "Create project" hoặc "Next".**
7.  **(Tùy chọn) Kết nối công cụ:** Jira có thể hỏi bạn muốn kết nối với các công cụ khác như Confluence (quản lý tài liệu) hay Bitbucket (quản lý code). Bạn có thể bỏ qua bước này ("Skip").
8.  **Hoàn tất:** Chúc mừng! Bạn đã tạo thành công Project Scrum đầu tiên của mình. Jira sẽ đưa bạn đến giao diện chính của dự án.

_(Giảng viên sẽ demo trực tiếp các bước này trên màn hình)_

#### 2.3. Cấu hình cơ bản sau khi tạo Project

Sau khi tạo Project, có một vài cấu hình cơ bản bạn có thể xem xét (thường nằm trong mục "Project settings" ở menu bên trái):

- **Details (Chi tiết):** Bạn có thể thay đổi lại Tên Project, Key (ít khi cần đổi sau khi đã tạo), Avatar (hình đại diện cho project).
- **Access (Quyền truy cập):** Ai có thể xem và làm việc trong project này? Với project Team-managed, bạn có thể dễ dàng mời thêm thành viên (bằng email) và quản lý quyền của họ (ví dụ: Administrator, Member). Ban đầu, có thể chỉ có bạn là thành viên.
- **Features (Tính năng):** Bạn có thể bật/tắt một số tính năng của Jira cho project này (ví dụ: Bật/tắt Reports, Releases...). Với mục đích học cơ bản, bạn chưa cần thay đổi nhiều ở đây.

#### 2.4. Giới thiệu các thành phần chính của Project Scrum

Khi vào một Project Scrum trên Jira, bạn sẽ thấy một số khu vực làm việc chính, thường ở menu bên trái:

- **Backlog:**
  - Đây là **trái tim của dự án Scrum**. Nó chứa danh sách **tất cả các công việc (Issues)** cần làm cho sản phẩm, được gọi là **Product Backlog**.
  - Nơi bạn sẽ tạo mới các yêu cầu (User Story), lỗi (Bug), công việc (Task).
  - Nơi bạn sắp xếp thứ tự ưu tiên cho công việc (việc nào quan trọng hơn làm trước).
  - Nơi bạn lập kế hoạch cho các **Sprint** (chọn những việc sẽ làm trong đợt làm việc tiếp theo).
- **Active Sprints (hoặc Board):**
  - Đây là **bảng công việc (Scrum Board)** hiển thị các công việc mà nhóm đang thực hiện trong **Sprint hiện tại**.
  - Thường có các cột thể hiện trạng thái công việc như: **To Do** (Cần làm), **In Progress** (Đang làm), **Done** (Đã xong).
  - Nhóm sẽ cập nhật trạng thái công việc bằng cách kéo thả các Issue qua lại giữa các cột này hàng ngày.
  - Giúp mọi người thấy rõ tiến độ của Sprint.
- **Reports (Báo cáo):**
  - Jira cung cấp nhiều loại báo cáo tự động để giúp nhóm theo dõi tiến độ và hiệu suất.
  - Một số báo cáo phổ biến cho Scrum:
    - **Burndown Chart:** Biểu đồ thể hiện lượng công việc còn lại trong Sprint theo thời gian (giúp xem nhóm có đang đi đúng tiến độ để hoàn thành Sprint không).
    - **Velocity Chart:** Biểu đồ thể hiện lượng công việc nhóm hoàn thành được trong các Sprint trước đó (giúp dự đoán khả năng của nhóm trong tương lai).
  - Ở mức cơ bản, bạn chỉ cần biết khu vực này tồn tại để xem các thống kê về dự án.
- **Issues:** Một danh sách hiển thị tất cả các Issue trong dự án, kèm theo bộ lọc để bạn tìm kiếm dễ dàng.

Chúng ta sẽ tìm hiểu kỹ hơn về cách sử dụng Backlog và Board ở các phần sau.

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Project Template (Mẫu Dự án):** Một bộ cấu hình và tính năng được thiết lập sẵn trong Jira để phù hợp với một quy trình làm việc cụ thể (như Scrum, Kanban).
- **Scrum / Kanban / Bug Tracking:** Tên của các quy trình/phương pháp quản lý công việc phổ biến.
- **Team-managed Project:** Loại project trong Jira Cloud, đơn giản, linh hoạt, do nhóm tự quản lý cấu hình.
- **Company-managed Project:** Loại project trong Jira Cloud, mạnh mẽ hơn, chia sẻ cấu hình chung, thường do quản trị viên Jira quản lý.
- **Project Name (Tên Project):** Tên đầy đủ, dễ hiểu của dự án.
- **Project Key (Khóa Project):** Một mã định danh ngắn gọn, duy nhất cho project, dùng trong ID của các Issue (ví dụ: `KEY-123`).
- **Project Settings (Cài đặt Dự án):** Khu vực để tùy chỉnh các thiết lập cho một project cụ thể.
- **Access (Quyền truy cập):** Quyền hạn của người dùng đối với project (ai được xem, ai được sửa...).
- **Backlog (Product Backlog):** Danh sách chứa tất cả các công việc (yêu cầu, lỗi, nhiệm vụ...) cần làm cho sản phẩm, được sắp xếp ưu tiên.
- **Active Sprint / Board (Bảng công việc Sprint):** Nơi hiển thị và theo dõi các công việc đang được thực hiện trong Sprint hiện tại.
- **To Do / In Progress / Done:** Các trạng thái phổ biến của công việc trên Board.
- **Reports (Báo cáo):** Các biểu đồ, thống kê tự động giúp theo dõi tiến độ và hiệu suất dự án.
- **Burndown Chart / Velocity Chart:** Tên của các loại báo cáo Scrum phổ biến trong Jira.
- **Issue:** Đơn vị công việc cơ bản trong Jira (sẽ học kỹ ở phần sau).

---

### 🧠 Câu hỏi thảo luận gợi mở

- Theo bạn, sự khác biệt chính giữa project "Team-managed" và "Company-managed" là gì? Khi nào nên dùng loại nào?
- Tại sao việc đặt "Project Key" lại quan trọng? Nó giúp ích gì trong quá trình làm việc?
- Nhìn vào các thành phần chính (Backlog, Board, Reports), bạn nghĩ thành phần nào sẽ được nhóm phát triển sử dụng thường xuyên nhất hàng ngày? Tại sao?

---

### 📌 Tài liệu & Tham khảo

- Tạo một project mới trong Jira Cloud (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/create-a-new-project/](https://support.atlassian.com/jira-software-cloud/docs/create-a-new-project/)
- Team-managed vs Company-managed projects (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/what-are-team-managed-and-company-managed-projects/](https://support.atlassian.com/jira-software-cloud/docs/what-are-team-managed-and-company-managed-projects/)
- Tìm hiểu về Scrum Board (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/understand-the-scrum-board/](https://support.atlassian.com/jira-software-cloud/docs/understand-the-scrum-board/)
- Tìm hiểu về Backlog (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/understand-the-backlog/](https://support.atlassian.com/jira-software-cloud/docs/understand-the-backlog/)
