## 4. Workflow cơ bản

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được **Workflow là gì** và tại sao nó quan trọng trong việc quản lý công việc.
- Nhận biết được **Workflow mặc định** thường thấy trong một Project Scrum trên Jira (ví dụ: To Do, In Progress, Done).
- Hiểu cách một **Issue di chuyển qua các trạng thái** khác nhau trên Scrum Board.
- Biết rằng có thể tùy chỉnh Workflow nhưng việc đó nằm ngoài phạm vi cơ bản.

---

### 🧩 Nội dung chi tiết

#### 4.1. Workflow là gì? Tại sao cần Workflow?

Bạn còn nhớ Scrum Board với các cột như "To Do", "In Progress", "Done" mà chúng ta đã thấy ở phần trước không? **Workflow (Luồng công việc)** chính là **con đường định sẵn** mà một Issue (công việc) phải đi qua từ lúc nó được tạo ra cho đến khi hoàn thành.

Hãy tưởng tượng Workflow giống như quy trình các bước bạn phải làm khi gửi một bưu kiện:

1.  **Chuẩn bị hàng (To Do):** Bạn đóng gói món hàng.
2.  **Đang vận chuyển (In Progress):** Bưu tá đến lấy hàng và đang trên đường giao.
3.  **Đã giao thành công (Done):** Người nhận đã nhận được hàng.

Mỗi bước này là một **Status (Trạng thái)** trong Workflow. Một Issue không thể nhảy cóc lung tung giữa các trạng thái, mà phải đi theo một **Transition (Chuyển tiếp)** được định nghĩa trước. Ví dụ, bạn không thể chuyển trạng thái từ "Chuẩn bị hàng" thẳng sang "Đã giao thành công" mà phải qua bước "Đang vận chuyển".

**Tại sao cần Workflow?**

- **Chuẩn hóa quy trình:** Đảm bảo mọi người trong nhóm đều tuân theo cùng một quy trình xử lý công việc, tránh việc mỗi người làm một kiểu.
- **Minh bạch hóa trạng thái:** Giúp mọi người dễ dàng biết được một công việc đang ở giai đoạn nào chỉ bằng cách nhìn vào Status của nó.
- **Kiểm soát quá trình:** Workflow có thể đặt ra các quy tắc (ví dụ: chỉ có Tester mới được chuyển Issue sang trạng thái "Ready for Testing") để đảm bảo chất lượng.
- **Tự động hóa (Nâng cao):** Có thể thiết lập các hành động tự động xảy ra khi Issue chuyển trạng thái (ví dụ: tự động gán việc cho Tester khi Issue chuyển sang "Ready for Testing").

#### 4.2. Workflow mặc định của Project Scrum

Khi bạn tạo một Project Scrum (đặc biệt là loại Team-managed), Jira thường cung cấp một Workflow rất đơn giản và phổ biến, bao gồm các trạng thái cơ bản sau:

- **TO DO (Cần làm):** Issue mới được tạo hoặc đã được lên kế hoạch nhưng chưa bắt đầu làm.
- **IN PROGRESS (Đang tiến hành):** Ai đó đã bắt đầu làm việc với Issue này.
- **DONE (Đã xong):** Công việc đã được hoàn thành theo định nghĩa hoàn thành (Definition of Done) của nhóm.

Đây là một Workflow rất cơ bản và dễ hiểu, phù hợp cho nhiều đội nhóm mới bắt đầu.

_(Lưu ý: Các Project Company-managed hoặc các template khác có thể có Workflow phức tạp hơn với nhiều trạng thái hơn, ví dụ: `Selected for Development`, `In Review`, `Ready for Testing`, `Blocked`...)_

#### 4.3. Cách Issue di chuyển qua các trạng thái trên Board

Cách phổ biến nhất để thay đổi trạng thái của một Issue (tức là di chuyển nó trong Workflow) là thông qua **Scrum Board**:

1.  Mở **Active Sprints** (hoặc Board) của Project.
2.  Bạn sẽ thấy các cột tương ứng với các Status trong Workflow (ví dụ: cột TO DO, cột IN PROGRESS, cột DONE).
3.  Các Issue (thẻ việc) sẽ nằm trong các cột tương ứng với trạng thái hiện tại của chúng.
4.  Để chuyển trạng thái một Issue, bạn chỉ cần **kéo và thả (drag and drop)** thẻ Issue đó từ cột hiện tại sang cột trạng thái mới.
    - Ví dụ: Khi bạn bắt đầu làm một việc trong cột "TO DO", bạn kéo thẻ Issue đó sang cột "IN PROGRESS".
    - Khi bạn làm xong, bạn kéo thẻ Issue đó sang cột "DONE".

Việc kéo thả này thực chất là bạn đang thực hiện một **Transition (Chuyển tiếp)** trong Workflow đã được định nghĩa sẵn.

Ngoài ra, bạn cũng có thể thay đổi Status của Issue khi xem chi tiết Issue đó, thường sẽ có một nút hoặc danh sách thả xuống hiển thị các trạng thái tiếp theo mà Issue có thể chuyển đến.

#### 4.4. Tùy chỉnh Workflow (Giới thiệu)

Jira cho phép bạn **tùy chỉnh Workflow** để phù hợp chính xác với quy trình làm việc của nhóm mình. Bạn có thể:

- Thêm các Status mới (ví dụ: "In Review", "Testing", "Deployed").
- Định nghĩa các Transition mới giữa các Status.
- Thêm các điều kiện, ràng buộc cho Transition (ví dụ: chỉ ai đó mới được chuyển trạng thái).
- Thêm các hành động tự động (Post Functions) khi chuyển trạng thái.

Tuy nhiên, việc tùy chỉnh Workflow (đặc biệt là trong các project Company-managed) thường đòi hỏi quyền quản trị viên Jira và hiểu biết sâu hơn về cách Jira hoạt động. **Trong khuôn khổ khóa học cơ bản này, chúng ta sẽ tập trung vào việc sử dụng Workflow mặc định đơn giản (To Do -> In Progress -> Done).**

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Workflow (Luồng công việc):** Quy trình các bước (trạng thái) mà một Issue đi qua từ lúc bắt đầu đến lúc kết thúc.
- **Status (Trạng thái):** Một bước cụ thể trong Workflow, thể hiện tình trạng hiện tại của Issue (ví dụ: To Do, In Progress, Done).
- **Transition (Chuyển tiếp):** Hành động di chuyển một Issue từ Status này sang Status khác. Việc kéo thả Issue trên Board là một cách thực hiện Transition.
- **Scrum Board:** Bảng hiển thị các Issue trong Sprint dưới dạng các cột tương ứng với các Status của Workflow.
- **Definition of Done (Định nghĩa Hoàn thành):** Một bộ tiêu chí rõ ràng mà nhóm thống nhất để xác định khi nào một công việc thực sự được coi là "Done".
- **Team-managed / Company-managed Project:** Hai loại project trong Jira Cloud với cách quản lý Workflow khác nhau (Team-managed đơn giản hơn, Company-managed mạnh mẽ và phức tạp hơn trong việc tùy chỉnh Workflow).

---

### 🧠 Câu hỏi thảo luận gợi mở

- Tại sao việc có một Workflow chuẩn lại quan trọng cho cả nhóm?
- Workflow mặc định "To Do -> In Progress -> Done" có đủ cho mọi loại dự án không? Khi nào bạn nghĩ cần thêm các trạng thái khác?
- Việc kéo thả Issue trên Board có ý nghĩa gì về mặt Workflow?

---

### 📌 Tài liệu & Tham khảo

- Tìm hiểu về Workflow (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/understand-workflows/](https://support.atlassian.com/jira-software-cloud/docs/understand-workflows/)
- Làm việc với Workflow trong project Team-managed (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/customize-the-workflow-in-team-managed-projects/](https://support.atlassian.com/jira-software-cloud/docs/customize-the-workflow-in-team-managed-projects/)
- Transition an issue (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/transition-an-issue/](https://support.atlassian.com/jira-software-cloud/docs/transition-an-issue/)
