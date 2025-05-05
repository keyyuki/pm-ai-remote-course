## 5. Sử dụng Backlog và Sprint/Kanban Board

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu rõ vai trò và cách sử dụng **Backlog** để quản lý danh sách công việc của sản phẩm.
- Biết cách **sắp xếp, ưu tiên** các Issue trong Backlog.
- Hiểu cách **tạo và quản lý Epic** để nhóm các công việc lớn.
- Được giới thiệu sơ lược về **ước lượng công việc (Estimation)** bằng Story Points.
- Hiểu khái niệm **Sprint** trong Scrum và cách **tạo Sprint** từ Backlog.
- Sử dụng thành thạo **Scrum Board** để **theo dõi tiến độ** công việc trong Sprint đang chạy (kéo thả Issue).
- Biết cách **hoàn thành một Sprint**.
- Được giới thiệu sơ qua về **Kanban Board** như một lựa chọn khác.

---

### 🧩 Nội dung chi tiết

#### 5.1. Backlog: Kho chứa công việc của dự án

**Backlog** (hay cụ thể hơn là **Product Backlog**) là nơi tập trung **toàn bộ danh sách các công việc** mà nhóm dự định sẽ làm cho sản phẩm trong tương lai. Nó giống như một danh sách "những điều ước" hoặc "những việc cần làm" cho sản phẩm, bao gồm:

- Các tính năng mới (User Story).
- Các cải tiến cho tính năng hiện có.
- Các công việc kỹ thuật (Task).
- Các lỗi cần sửa (Bug).

**Đặc điểm chính của Backlog:**

- **Động (Dynamic):** Backlog không cố định mà liên tục thay đổi. Yêu cầu mới có thể được thêm vào, yêu cầu cũ có thể bị loại bỏ hoặc thay đổi độ ưu tiên.
- **Được sắp xếp ưu tiên (Prioritized):** Các công việc quan trọng nhất, mang lại giá trị cao nhất hoặc cần làm sớm nhất sẽ được xếp lên đầu danh sách. Product Owner (người đại diện cho khách hàng/người dùng) thường chịu trách nhiệm chính trong việc sắp xếp này.
- **Chứa mọi thứ:** Bất cứ công việc nào liên quan đến sản phẩm mà có thể cần làm trong tương lai đều nên được đưa vào Backlog để không bị bỏ sót.

**Cách sử dụng Backlog trong Jira:**

1.  **Truy cập:** Trong Project Scrum của bạn, chọn mục "Backlog" ở menu bên trái.
2.  **Xem danh sách:** Bạn sẽ thấy danh sách các Issue (Story, Bug, Task) chưa được đưa vào Sprint nào.
3.  **Tạo Issue mới:** Bạn có thể nhanh chóng tạo Issue mới ngay tại cuối danh sách Backlog.
4.  **Sắp xếp ưu tiên:** Kéo và thả các Issue lên hoặc xuống trong danh sách để thay đổi thứ tự ưu tiên. Issue ở trên cùng là ưu tiên cao nhất.
5.  **Xem chi tiết:** Nhấp vào một Issue để xem và chỉnh sửa thông tin chi tiết của nó.

**Quản lý Epic trong Backlog:**

- Epic (nhóm công việc lớn) thường được quản lý trong một panel (khung) riêng bên cạnh Backlog (thường là bên trái).
- Bạn có thể tạo Epic mới từ panel này.
- Để thêm một Issue (Story, Task, Bug) vào một Epic, bạn có thể kéo Issue từ Backlog thả vào Epic trong panel, hoặc mở chi tiết Issue và chọn Epic trong trường "Epic Link".
- Việc này giúp bạn nhóm các công việc liên quan lại với nhau một cách trực quan.

**Ước lượng (Estimation) - Giới thiệu Story Points:**

- Trong Scrum, nhóm thường **ước lượng độ lớn hoặc độ phức tạp** của các User Story để lập kế hoạch tốt hơn. Việc này _không phải_ là ước lượng thời gian (giờ, ngày) mà là ước lượng **tương đối**.
- Đơn vị phổ biến là **Story Points**. Nhóm sẽ gán một con số (thường theo dãy Fibonacci: 1, 2, 3, 5, 8, 13...) cho mỗi Story, thể hiện mức độ phức tạp, khối lượng công việc và rủi ro của nó so với các Story khác.
  - Ví dụ: Một Story đơn giản có thể là 1 point, một Story phức tạp hơn nhiều có thể là 8 points.
- Trong Jira, bạn có thể nhập giá trị Story Points vào trường "Story point estimate" của Issue.
- Việc ước lượng này giúp nhóm biết được họ có thể nhận bao nhiêu công việc vào một Sprint (dựa trên kinh nghiệm từ các Sprint trước - gọi là Velocity).
- **Lưu ý:** Việc ước lượng bằng Story Points là một kỹ thuật cần thực hành nhiều. Ở mức cơ bản, bạn chỉ cần biết khái niệm này tồn tại và có trường để nhập trong Jira.

#### 5.2. Sprint và Scrum Board: Thực thi và Theo dõi

**Sprint là gì?**

- Như đã học ở Module 1, **Sprint** là một khoảng thời gian cố định (thường từ 1 đến 4 tuần) mà nhóm Scrum tập trung làm việc để hoàn thành một lượng công việc đã chọn từ Backlog.
- Mục tiêu của mỗi Sprint là tạo ra một phần sản phẩm có giá trị, có thể sử dụng được (gọi là Increment).

**Tạo Sprint từ Backlog:**

1.  Trong màn hình Backlog, bạn sẽ thấy một khu vực ở trên cùng dành cho Sprint sắp tới (hoặc Sprint đang chạy).
2.  Nhấn nút **"Create Sprint"**. Một Sprint mới (ví dụ: "Sprint 1") sẽ được tạo ra.
3.  **Kéo và thả** các Issue (đã được ưu tiên và ước lượng) từ Backlog vào khu vực Sprint vừa tạo. Đây chính là quá trình **Sprint Planning** - lựa chọn công việc cho Sprint.
4.  Khi đã chọn đủ công việc mà nhóm nghĩ có thể hoàn thành, nhấn nút **"Start Sprint"**.
5.  Jira sẽ yêu cầu bạn xác nhận Tên Sprint và Thời lượng (ví dụ: 2 tuần). Nhấn "Start".

**Sử dụng Scrum Board (Active Sprints):**

- Sau khi bắt đầu Sprint, bạn sẽ được chuyển đến màn hình **Active Sprints** (hoặc **Board**). Đây là nơi nhóm theo dõi tiến độ công việc hàng ngày.
- Board hiển thị các cột tương ứng với các trạng thái trong Workflow (To Do, In Progress, Done).
- Các Issue bạn đã chọn cho Sprint sẽ xuất hiện trên Board, thường là ở cột "To Do".
- **Hàng ngày (trong Daily Scrum):** Các thành viên sẽ cập nhật trạng thái công việc của mình bằng cách **kéo thả** các Issue qua các cột:
  - Khi bắt đầu làm một việc -> Kéo từ "To Do" sang "In Progress".
  - Khi hoàn thành một việc -> Kéo từ "In Progress" sang "Done".
- Board giúp cả nhóm nhìn thấy rõ ràng:
  - Ai đang làm việc gì?
  - Công việc nào đang tiến triển?
  - Công việc nào đã hoàn thành?
  - Có công việc nào đang bị tắc nghẽn không?

**Hoàn thành Sprint (Complete Sprint):**

- Khi hết thời gian Sprint (ví dụ: hết 2 tuần), nhóm sẽ tiến hành **Sprint Review** (trình bày những gì đã làm được) và **Sprint Retrospective** (nhìn lại quá trình làm việc để cải tiến).
- Trên Scrum Board, người có quyền (thường là Scrum Master hoặc Project Lead) sẽ nhấn nút **"Complete Sprint"**.
- Jira sẽ hiển thị một bảng tóm tắt các Issue đã hoàn thành và chưa hoàn thành trong Sprint.
- Các Issue **chưa hoàn thành** sẽ được hỏi bạn muốn chuyển chúng về lại **Backlog** hay chuyển sang **Sprint tiếp theo** (thường là chuyển về Backlog để được đánh giá lại độ ưu tiên).
- Nhấn "Complete". Sprint kết thúc và bạn có thể bắt đầu chu kỳ mới với Sprint tiếp theo.

**Giới thiệu Kanban Board:**

- Ngoài Scrum Board, Jira còn hỗ trợ **Kanban Board**. Kanban tập trung vào việc **trực quan hóa luồng công việc liên tục** và **giới hạn số lượng công việc đang thực hiện** (Work In Progress - WIP) trong mỗi trạng thái để tránh tắc nghẽn.
- Kanban Board không có khái niệm Sprint cố định. Công việc được kéo từ Backlog vào cột đầu tiên của Board và di chuyển qua các cột cho đến khi hoàn thành.
- Kanban phù hợp cho các nhóm có công việc đến liên tục và không theo chu kỳ cố định như đội hỗ trợ, bảo trì, hoặc các nhóm muốn quy trình linh hoạt hơn Scrum.
- Bạn có thể tạo Project theo template Kanban hoặc chuyển đổi Board của Project Scrum sang dạng Kanban nếu muốn khám phá.

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Backlog (Product Backlog):** Danh sách ưu tiên chứa tất cả công việc cần làm cho sản phẩm.
- **Prioritize (Ưu tiên hóa):** Sắp xếp công việc theo thứ tự quan trọng.
- **Epic:** Nhóm công việc lớn.
- **Estimation (Ước lượng):** Đánh giá độ lớn/phức tạp của công việc.
- **Story Points:** Đơn vị đo lường tương đối độ phức tạp/khối lượng công việc của User Story.
- **Velocity:** Thước đo lượng công việc (thường tính bằng Story Points) mà nhóm hoàn thành được trong một Sprint.
- **Sprint:** Một khoảng thời gian cố định (1-4 tuần) để nhóm hoàn thành một lượng công việc đã chọn.
- **Increment:** Phần sản phẩm có giá trị, có thể sử dụng được, tạo ra sau mỗi Sprint.
- **Sprint Planning:** Buổi họp để lập kế hoạch cho Sprint, chọn công việc từ Backlog vào Sprint Backlog.
- **Sprint Backlog:** Danh sách các công việc đã được chọn để thực hiện trong Sprint hiện tại.
- **Scrum Board / Active Sprints:** Bảng trực quan hóa và theo dõi công việc trong Sprint đang chạy.
- **Daily Scrum:** Cuộc họp ngắn hàng ngày để nhóm đồng bộ tiến độ và kế hoạch.
- **Complete Sprint:** Hành động kết thúc Sprint trong Jira.
- **Sprint Review:** Buổi họp cuối Sprint để trình bày Increment và thu thập phản hồi.
- **Sprint Retrospective:** Buổi họp cuối Sprint để nhóm nhìn lại quy trình làm việc và tìm cách cải tiến.
- **Kanban Board:** Bảng trực quan hóa luồng công việc liên tục, tập trung vào giới hạn WIP.
- **Work In Progress (WIP):** Số lượng công việc đang được thực hiện dang dở tại một thời điểm.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Tại sao việc sắp xếp ưu tiên Backlog lại quan trọng? Ai nên là người quyết định thứ tự ưu tiên?
- Sự khác biệt chính giữa Backlog và Sprint Backlog là gì?
- Việc kéo thả Issue trên Scrum Board hàng ngày mang lại lợi ích gì cho nhóm?
- Điều gì xảy ra với những công việc chưa hoàn thành khi Sprint kết thúc?
- Khi nào thì nên dùng Scrum Board, khi nào thì Kanban Board có thể phù hợp hơn?

---

### 📌 Tài liệu & Tham khảo

- Tìm hiểu về Backlog (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/understand-the-backlog/](https://support.atlassian.com/jira-software-cloud/docs/understand-the-backlog/)
- Ước lượng bằng Story Points (Atlassian): [https://www.atlassian.com/agile/project-management/estimation](https://www.atlassian.com/agile/project-management/estimation)
- Lập kế hoạch Sprint (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/plan-a-sprint/](https://support.atlassian.com/jira-software-cloud/docs/plan-a-sprint/)
- Bắt đầu và Hoàn thành Sprint (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/start-and-complete-a-sprint/](https://support.atlassian.com/jira-software-cloud/docs/start-and-complete-a-sprint/)
- Tìm hiểu về Scrum Board (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/understand-the-scrum-board/](https://support.atlassian.com/jira-software-cloud/docs/understand-the-scrum-board/)
- Tìm hiểu về Kanban Board (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/understand-the-kanban-board/](https://support.atlassian.com/jira-software-cloud/docs/understand-the-kanban-board/)
