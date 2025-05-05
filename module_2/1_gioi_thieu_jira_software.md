## 1. Giới thiệu Jira Software

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được **Jira Software là gì** và vai trò của nó trong việc quản lý dự án phần mềm.
- Phân biệt được các **phiên bản Jira** phổ biến và lý do tập trung vào Jira Cloud.
- Nắm được những **lợi ích chính** khi sử dụng Jira cho đội nhóm phát triển phần mềm.
- Nhận biết các **thành phần giao diện cơ bản** của Jira Software.
- Biết cách **đăng ký một tài khoản Jira Cloud miễn phí** để chuẩn bị thực hành.

---

### 🧩 Nội dung chi tiết

#### 1.1. Jira Software là gì?

Hãy tưởng tượng bạn và nhóm bạn đang cùng nhau thực hiện một dự án lớn, ví dụ như tổ chức một sự kiện hoặc xây dựng một website. Có rất nhiều việc cần làm: ai làm việc gì? việc nào xong rồi? việc nào đang gặp khó khăn?

**Jira Software** giống như một **bảng kế hoạch công việc kỹ thuật số siêu mạnh mẽ** dành cho các đội nhóm, đặc biệt là các đội phát triển phần mềm. Nó giúp mọi người:

- **Theo dõi tất cả công việc:** Từ những ý tưởng lớn đến các nhiệm vụ nhỏ nhất.
- **Biết ai đang làm gì:** Phân công công việc rõ ràng.
- **Nắm bắt tiến độ:** Xem công việc đang ở giai đoạn nào (ví dụ: Mới bắt đầu, Đang làm, Đã xong).
- **Phát hiện và quản lý vấn đề:** Ghi nhận lỗi (bug) hoặc các khó khăn gặp phải.
- **Hợp tác hiệu quả:** Mọi người cùng nhìn vào một chỗ để biết tình hình chung của dự án.

Nó được phát triển bởi công ty **Atlassian** và là một trong những công cụ quản lý dự án phổ biến nhất thế giới, đặc biệt trong các dự án áp dụng **Agile/Scrum** (những phương pháp làm việc linh hoạt mà chúng ta đã tìm hiểu ở Module 1).

#### 1.2. Các phiên bản Jira

Jira có một vài phiên bản chính, nhưng chúng ta sẽ tập trung vào **Jira Cloud**:

- **Jira Cloud:**
  - Đây là phiên bản **chạy trên nền tảng web** (giống như Gmail hay Facebook). Bạn chỉ cần trình duyệt và internet để truy cập.
  - **Ưu điểm:** Dễ dàng bắt đầu, không cần cài đặt phức tạp, luôn được cập nhật tính năng mới nhất, có gói **miễn phí** cho các đội nhóm nhỏ (rất phù hợp để học và thực hành!).
  - **Đây là phiên bản chúng ta sẽ sử dụng trong suốt khóa học.**
- **Jira Data Center:**
  - Phiên bản này dành cho các **tổ chức lớn**, cần tự quản lý hạ tầng máy chủ của riêng mình để có quyền kiểm soát cao hơn về dữ liệu và hiệu năng.
  - Yêu cầu kiến thức kỹ thuật để cài đặt và vận hành.
- **Jira Server (Đã ngừng bán cho khách hàng mới):**
  - Tương tự Data Center nhưng là phiên bản cũ hơn, các công ty tự cài đặt trên máy chủ của họ. Atlassian đang khuyến khích chuyển sang Cloud hoặc Data Center.

**Tại sao tập trung vào Jira Cloud?** Vì nó dễ tiếp cận nhất cho người mới bắt đầu, không tốn chi phí ban đầu và là xu hướng được nhiều công ty lựa chọn hiện nay.

#### 1.3. Tại sao dùng Jira cho dự án phần mềm? Lợi ích chính

Việc sử dụng một công cụ như Jira mang lại nhiều lợi ích cho đội ngũ phát triển phần mềm:

- **Minh bạch (Transparency):** Mọi người trong nhóm (và cả quản lý, khách hàng nếu được mời) đều có thể thấy được bức tranh tổng thể của dự án: công việc nào đang được thực hiện, ai đang làm, tiến độ ra sao.
- **Quản lý tập trung (Centralized Management):** Tất cả thông tin về công việc, yêu cầu, lỗi, thảo luận... được lưu trữ ở một nơi duy nhất, tránh thất lạc thông tin qua email, chat,...
- **Hỗ trợ quy trình Agile/Scrum:** Jira được thiết kế tối ưu cho các phương pháp làm việc linh hoạt như Scrum và Kanban (một phương pháp trực quan hóa công việc khác). Nó có sẵn các công cụ như Backlog, Sprint Board giúp việc thực hành Agile trở nên dễ dàng hơn.
- **Theo dõi tiến độ hiệu quả:** Dễ dàng xem các báo cáo, biểu đồ để biết dự án đang chạy nhanh hay chậm, có gặp vấn đề gì không.
- **Cải thiện sự hợp tác (Collaboration):** Các thành viên có thể bình luận, cập nhật trạng thái công việc, đính kèm tài liệu ngay trên từng nhiệm vụ (Issue).

#### 1.4. Giao diện tổng quan

Khi bạn đăng nhập vào Jira Cloud, bạn sẽ thấy một số khu vực chính (chúng ta sẽ tìm hiểu kỹ hơn trong các phần sau):

- **Projects (Dự án):** Giống như một thư mục lớn chứa tất cả công việc liên quan đến một sản phẩm hoặc mục tiêu cụ thể. Mỗi dự án có thể có cách thiết lập riêng.
- **Issues (Vấn đề/Nhiệm vụ):** Đây là đơn vị công việc cơ bản trong Jira. Một Issue có thể là một **User Story** (yêu cầu người dùng), một **Task** (nhiệm vụ cụ thể), một **Bug** (lỗi phần mềm), hoặc một **Epic** (một nhóm công việc lớn).
- **Boards (Bảng):** Nơi trực quan hóa quy trình làm việc. Có 2 loại bảng phổ biến:
  - **Scrum Board:** Dành cho các nhóm làm việc theo Sprint, có Backlog và các cột trạng thái (To Do, In Progress, Done).
  - **Kanban Board:** Hiển thị luồng công việc liên tục, tập trung vào việc giới hạn số lượng công việc đang thực hiện cùng lúc.
- **Dashboards (Bảng điều khiển):** Nơi hiển thị các biểu đồ, thống kê tổng quan về tiến độ dự án, giống như bảng đồng hồ trên xe hơi cho bạn biết các thông số quan trọng.
- **Filters (Bộ lọc):** Công cụ để tìm kiếm và xem các Issue theo những tiêu chí nhất định (ví dụ: xem tất cả Bug, xem các Task của bạn).

#### 1.5. Cài đặt tài khoản Jira Cloud (miễn phí)

Để thực hành, bạn cần có tài khoản Jira Cloud. Atlassian cung cấp gói miễn phí rất tốt cho nhóm dưới 10 người.

**Các bước đăng ký:**

1.  Truy cập trang web của Atlassian Jira Software: [https://www.atlassian.com/software/jira](https://www.atlassian.com/software/jira)
2.  Tìm và nhấp vào nút đăng ký hoặc dùng thử miễn phí (Thường là "Get it free" hoặc tương tự).
3.  Bạn sẽ được yêu cầu đăng ký tài khoản Atlassian (nếu chưa có) bằng email hoặc tài khoản Google/Microsoft.
4.  Làm theo các bước hướng dẫn để tạo "site" Jira của bạn (ví dụ: `tenban.atlassian.net`). Hãy chọn một tên dễ nhớ.
5.  Trong quá trình thiết lập, Jira có thể hỏi bạn về loại dự án bạn muốn tạo hoặc mời thành viên nhóm. Bạn có thể bỏ qua các bước này hoặc chọn tạo một dự án Scrum mẫu để khám phá trước.
6.  Sau khi hoàn tất, bạn sẽ được chuyển đến giao diện Jira Cloud của mình.

**Lưu ý:** Giao diện và các bước đăng ký có thể thay đổi một chút theo thời gian, nhưng quy trình cơ bản là tương tự. Hãy đọc kỹ các hướng dẫn trên màn hình.

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Jira / Jira Software:** Tên của phần mềm quản lý dự án của công ty Atlassian.
- **Atlassian:** Tên công ty tạo ra Jira, Confluence, Bitbucket và nhiều công cụ khác cho đội nhóm.
- **Issue (Vấn đề/Nhiệm vụ):** Đơn vị công việc cơ bản trong Jira (có thể là yêu cầu, lỗi, nhiệm vụ...). Giống như một "thẻ việc" cần xử lý.
- **Project (Dự án):** Một không gian làm việc trong Jira để quản lý một tập hợp các Issue liên quan đến một mục tiêu hoặc sản phẩm cụ thể.
- **Board (Bảng):** Cách hiển thị trực quan các Issue và trạng thái của chúng (ví dụ: To Do, In Progress, Done).
- **Dashboard (Bảng điều khiển):** Trang tổng hợp các biểu đồ, thống kê về dự án.
- **Cloud (Điện toán đám mây):** Phần mềm được chạy trên máy chủ của nhà cung cấp và bạn truy cập qua internet (không cần cài đặt trên máy tính của bạn).
- **Data Center / Server:** Phiên bản Jira mà công ty phải tự cài đặt và quản lý trên máy chủ của riêng họ.
- **Agile / Scrum:** Các phương pháp quản lý dự án linh hoạt, tập trung vào việc chia nhỏ công việc, hợp tác liên tục và thích ứng với thay đổi (đã học ở Module 1).
- **Workflow (Luồng công việc):** Các bước hoặc trạng thái mà một Issue di chuyển qua từ lúc bắt đầu đến lúc hoàn thành (ví dụ: To Do -> In Progress -> Done).
- **Backlog:** Danh sách các công việc (Issue) cần làm cho sản phẩm, được sắp xếp theo thứ tự ưu tiên.
- **Sprint:** Một khoảng thời gian cố định (thường 1-4 tuần) mà nhóm Scrum làm việc để hoàn thành một lượng công việc đã chọn.
- **Kanban:** Một phương pháp quản lý công việc khác tập trung vào việc trực quan hóa luồng công việc và giới hạn công việc đang thực hiện.
- **User Story, Task, Bug, Epic:** Các loại Issue phổ biến trong Jira để phân loại công việc (sẽ học kỹ hơn ở phần sau).

---

### 🧠 Câu hỏi thảo luận gợi mở

- Trước khi biết đến Jira, bạn hoặc nhóm của bạn thường theo dõi công việc chung bằng cách nào (ví dụ: giấy nhớ, Excel, Zalo...)? Cách đó có gặp khó khăn gì không?
- Theo bạn, lợi ích nào của Jira là quan trọng nhất đối với một nhóm sinh viên đang làm đồ án tốt nghiệp?
- Bạn nghĩ việc mọi người cùng thấy được công việc của nhau trên Jira có ưu điểm và nhược điểm gì?

---

### 📌 Tài liệu & Tham khảo

- Trang chủ Jira Software: [https://www.atlassian.com/software/jira](https://www.atlassian.com/software/jira)
- Hướng dẫn bắt đầu với Jira Software Cloud (Atlassian): [https://support.atlassian.com/jira-software-cloud/resources/](https://support.atlassian.com/jira-software-cloud/resources/)
- What is Jira? (Atlassian): [https://www.atlassian.com/software/jira/guides/getting-started/what-is-jira](https://www.atlassian.com/software/jira/guides/getting-started/what-is-jira)
