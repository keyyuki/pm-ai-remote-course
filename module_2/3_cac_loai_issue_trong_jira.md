## 3. Các loại Issue trong Jira

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được **Issue là gì** trong Jira và tại sao nó lại là đơn vị công việc trung tâm.
- Phân biệt được các **loại Issue mặc định** phổ biến trong template Scrum: Epic, Story, Task, Bug, Sub-task.
- Biết cách **tạo mới một Issue** và **chỉnh sửa thông tin** của Issue đã có.
- Nhận biết và hiểu ý nghĩa của các **trường thông tin quan trọng** trên một Issue.

---

### 🧩 Nội dung chi tiết

#### 3.1. Khái niệm Issue và tầm quan trọng

Trong Jira, **Issue** là thuật ngữ chung để chỉ **bất kỳ đơn vị công việc nào** cần được theo dõi trong một dự án. Hãy nghĩ về nó như một "thẻ việc" (giống như một tờ giấy nhớ trên bảng) đại diện cho một điều gì đó cần được hoàn thành hoặc giải quyết.

Một Issue có thể là:

- Một **yêu cầu tính năng mới** từ khách hàng (ví dụ: "Người dùng cần có thể đăng nhập bằng Google").
- Một **công việc cụ thể** mà lập trình viên cần làm (ví dụ: "Viết code cho chức năng đăng nhập").
- Một **lỗi phần mềm** được phát hiện (ví dụ: "Nút đăng nhập không hoạt động trên trình duyệt Firefox").
- Một **câu hỏi cần trả lời** hoặc một **quyết định cần đưa ra**.

**Tại sao Issue lại quan trọng?**

- **Trung tâm của mọi thứ:** Hầu hết mọi hoạt động trong Jira đều xoay quanh các Issue. Bạn tạo Issue, phân công Issue, cập nhật trạng thái Issue, thảo luận trên Issue, liên kết Issue với nhau...
- **Minh bạch hóa công việc:** Mỗi Issue ghi lại rõ ràng công việc cần làm là gì, ai chịu trách nhiệm, tình trạng hiện tại ra sao.
- **Dễ dàng theo dõi:** Thay vì quản lý công việc qua email hay chat dễ bị trôi thông tin, Jira giúp tập trung mọi thứ liên quan đến một công việc vào một Issue duy nhất.
- **Cơ sở cho báo cáo:** Dữ liệu từ các Issue (trạng thái, thời gian hoàn thành...) được dùng để tạo ra các báo cáo tiến độ dự án.

#### 3.2. Phân biệt các loại Issue mặc định trong template Scrum

Khi bạn tạo một Project Scrum, Jira thường cung cấp sẵn một số **Issue Type (Loại Issue)** để bạn phân loại công việc. Việc phân loại này giúp tổ chức công việc tốt hơn và áp dụng các quy trình khác nhau nếu cần. Dưới đây là các loại phổ biến nhất:

1.  **Epic (Sử thi):**

    - **Mô tả:** Đại diện cho một **nhóm công việc lớn**, một **tính năng chính** hoặc một **sáng kiến lớn** mà thường không thể hoàn thành trong một Sprint duy nhất. Nó quá lớn để làm ngay lập tức.
    - **Ví dụ:** "Quản lý Hồ sơ Người dùng", "Tích hợp Thanh toán Online", "Xây dựng ứng dụng Di động".
    - **Mục đích:** Giúp chia nhỏ các mục tiêu lớn thành các phần nhỏ hơn (User Story) dễ quản lý hơn. Cung cấp cái nhìn tổng quan về các tính năng lớn của sản phẩm.

2.  **User Story (Câu chuyện Người dùng) / Story:**

    - **Mô tả:** Mô tả một **yêu cầu hoặc tính năng** từ góc nhìn của **người dùng cuối**. Thường được viết theo cấu trúc: "Là một [vai trò người dùng], tôi muốn [làm gì đó] để [đạt được lợi ích gì đó]".
    - **Ví dụ:** "Là một người mua hàng, tôi muốn có thể thêm sản phẩm vào giỏ hàng để có thể mua nhiều món cùng lúc."
    - **Mục đích:** Giúp đội phát triển hiểu rõ yêu cầu và giá trị mang lại cho người dùng. Đây là đơn vị công việc chính thường được đưa vào Sprint để thực hiện.
    - Một Epic thường bao gồm nhiều User Story.

3.  **Task (Nhiệm vụ):**

    - **Mô tả:** Một **công việc cụ thể** cần được hoàn thành, không nhất thiết phải mang lại giá trị trực tiếp cho người dùng cuối nhưng cần thiết cho dự án.
    - **Ví dụ:** "Thiết kế cơ sở dữ liệu cho chức năng giỏ hàng", "Nâng cấp thư viện ABC lên phiên bản mới", "Viết tài liệu hướng dẫn cài đặt".
    - **Mục đích:** Theo dõi các công việc kỹ thuật, hành chính hoặc các việc không phải là yêu cầu người dùng trực tiếp.

4.  **Bug (Lỗi):**

    - **Mô tả:** Một **vấn đề, lỗi hoặc khiếm khuyết** trong phần mềm khiến nó không hoạt động như mong đợi.
    - **Ví dụ:** "Nút 'Thanh toán' bị mờ đi sau khi thêm sản phẩm thứ hai vào giỏ", "Trang chủ bị lỗi hiển thị trên điện thoại iPhone X".
    - **Mục đích:** Ghi nhận và theo dõi quá trình sửa lỗi.

5.  **Sub-task (Nhiệm vụ con):**
    - **Mô tả:** Một **công việc nhỏ hơn**, chi tiết hơn được **chia ra từ một Issue cha** (thường là Story, Task hoặc Bug).
    - **Ví dụ:** Nếu Issue cha là Story "Xây dựng trang đăng nhập", các Sub-task có thể là: "Thiết kế giao diện đăng nhập", "Viết code xử lý logic đăng nhập", "Viết Unit Test cho chức năng đăng nhập".
    - **Mục đích:** Giúp chia nhỏ công việc phức tạp thành các bước dễ quản lý hơn, dễ phân công cho nhiều người hơn và theo dõi tiến độ chi tiết hơn.

**Mối quan hệ:** Thường thì một Epic sẽ chứa nhiều Story. Một Story (hoặc Task, Bug) có thể được chia thành nhiều Sub-task.

#### 3.3. Cách tạo và chỉnh sửa Issue

**Tạo Issue:**

Có nhiều cách để tạo Issue mới trong Jira, cách phổ biến nhất là:

1.  **Nút "Create" trên thanh điều hướng:** Nhấn vào nút "Create" (Thường có biểu tượng dấu +) ở thanh menu trên cùng.
2.  **Trong Backlog:** Di chuột đến cuối danh sách Backlog và nhấn vào "+ Create issue".
3.  **Trên Board (trong Sprint):** Một số Board cho phép tạo nhanh Issue trực tiếp trên cột.

Khi nhấn nút "Create", một hộp thoại sẽ hiện ra yêu cầu bạn nhập các thông tin:

- **Project:** Chọn đúng Project bạn muốn tạo Issue vào (thường đã được chọn sẵn nếu bạn đang ở trong Project đó).
- **Issue Type:** Chọn loại Issue bạn muốn tạo (Epic, Story, Task, Bug...). **Quan trọng:** Chọn đúng loại!
- **Summary (Tóm tắt):** Tiêu đề ngắn gọn, súc tích mô tả Issue. Đây là dòng bạn sẽ thấy trên Backlog và Board. **Bắt buộc phải có.**
- **Description (Mô tả):** Mô tả chi tiết hơn về Issue. Cung cấp ngữ cảnh, tiêu chí chấp nhận (Acceptance Criteria) cho Story, các bước tái hiện lỗi cho Bug...
- **Assignee (Người thực hiện):** Chọn người sẽ chịu trách nhiệm làm Issue này.
- **Reporter (Người báo cáo):** Người tạo ra Issue (thường là bạn).
- **Priority (Độ ưu tiên):** Mức độ quan trọng của Issue (Highest, High, Medium, Low, Lowest).
- **Labels (Nhãn):** Gắn các từ khóa để nhóm các Issue liên quan (ví dụ: "UI", "backend", "release-1.0").
- **Sprint:** Nếu tạo từ Backlog, bạn có thể chọn luôn Sprint sẽ làm Issue này (hoặc để trống).
- **Epic Link (Liên kết Epic):** Nếu là Story/Task/Bug, bạn có thể chọn Epic cha chứa nó.
- **Và nhiều trường khác...** (Tùy thuộc vào cấu hình Project)

Nhấn **"Create"** để hoàn tất.

**Chỉnh sửa Issue:**

1.  Mở Issue bạn muốn sửa bằng cách nhấp vào tiêu đề (Summary) của nó trên Backlog, Board hoặc danh sách Issues.
2.  Giao diện chi tiết của Issue sẽ hiện ra.
3.  Nhấp trực tiếp vào các trường thông tin (Summary, Description, Assignee, Priority...) để chỉnh sửa.
4.  Jira thường tự động lưu thay đổi của bạn.

#### 3.4. Các trường thông tin quan trọng

Hiểu rõ các trường thông tin trên một Issue giúp bạn quản lý công việc hiệu quả:

- **Summary (Tóm tắt):** Luôn giữ cho nó ngắn gọn và rõ ràng. Đây là thứ mọi người nhìn thấy đầu tiên.
- **Description (Mô tả):** Cung cấp đủ thông tin để người thực hiện hiểu cần làm gì. Với User Story, nên có Acceptance Criteria (tiêu chí nghiệm thu). Với Bug, cần có các bước tái hiện lỗi, kết quả mong đợi, kết quả thực tế.
- **Assignee (Người thực hiện):** Ai là người chịu trách nhiệm chính cho việc hoàn thành Issue này? Giúp làm rõ trách nhiệm.
- **Reporter (Người báo cáo):** Ai là người tạo ra Issue? Hữu ích để biết hỏi ai nếu cần làm rõ thông tin.
- **Priority (Độ ưu tiên):** Giúp sắp xếp thứ tự công việc. Issue nào cần làm trước?
- **Status (Trạng thái):** Issue đang ở giai đoạn nào trong quy trình làm việc (ví dụ: To Do, In Progress, In Review, Done)? Trạng thái này thường được cập nhật khi bạn kéo thả Issue trên Board.
- **Resolution (Kết quả xử lý):** Khi một Issue được chuyển sang trạng thái "Done", trường này cho biết kết quả cuối cùng (ví dụ: Fixed, Won't Fix, Duplicate, Done...).
- **Due Date (Ngày hết hạn):** Ngày mà Issue cần được hoàn thành (không phải lúc nào cũng dùng trong Scrum, nhưng hữu ích cho một số Task).
- **Labels (Nhãn):** Giúp lọc và tìm kiếm Issue theo chủ đề.
- **Epic Link:** Cho biết Story/Task/Bug này thuộc về Epic nào.
- **Linked Issues (Issue liên kết):** Cho thấy mối quan hệ với các Issue khác (ví dụ: Issue này bị chặn bởi Issue kia, Issue này là trùng lặp của Issue kia...).
- **Components (Thành phần):** Phân loại Issue theo các bộ phận, module của sản phẩm (ví dụ: "Login Module", "Payment Gateway").
- **Original Estimate / Remaining Estimate / Time Spent:** Các trường dùng để theo dõi thời gian ước lượng và thời gian thực tế bỏ ra (thường dùng nếu nhóm theo dõi công việc theo giờ).
- **Story Points (Điểm câu chuyện):** Một đơn vị đo lường độ phức tạp hoặc khối lượng công việc tương đối của một User Story (thường dùng trong Scrum để ước lượng).

_(Không phải tất cả các trường này đều hiển thị mặc định, tùy thuộc vào cấu hình Project và màn hình Issue)_

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Issue:** Đơn vị công việc cơ bản trong Jira (Story, Task, Bug...).
- **Issue Type (Loại Issue):** Cách phân loại Issue (Epic, Story, Task, Bug, Sub-task).
- **Epic:** Một nhóm công việc lớn, một tính năng chính.
- **User Story / Story:** Mô tả yêu cầu từ góc nhìn người dùng.
- **Task:** Một công việc cụ thể cần làm.
- **Bug:** Lỗi phần mềm.
- **Sub-task:** Công việc con được chia nhỏ từ một Issue cha.
- **Summary (Tóm tắt):** Tiêu đề ngắn gọn của Issue.
- **Description (Mô tả):** Nội dung chi tiết của Issue.
- **Acceptance Criteria (Tiêu chí nghiệm thu):** Các điều kiện cần đáp ứng để coi một User Story là hoàn thành.
- **Assignee (Người thực hiện):** Người được giao làm Issue.
- **Reporter (Người báo cáo):** Người tạo ra Issue.
- **Priority (Độ ưu tiên):** Mức độ quan trọng của Issue.
- **Status (Trạng thái):** Giai đoạn hiện tại của Issue trong quy trình (To Do, In Progress...).
- **Resolution (Kết quả xử lý):** Kết quả cuối cùng khi Issue đóng lại (Fixed, Done...).
- **Due Date (Ngày hết hạn):** Hạn chót hoàn thành Issue.
- **Labels (Nhãn):** Từ khóa để phân loại, nhóm Issue.
- **Epic Link:** Liên kết từ Story/Task/Bug đến Epic cha.
- **Linked Issues:** Các liên kết thể hiện mối quan hệ giữa các Issue.
- **Components:** Các bộ phận, module của sản phẩm.
- **Estimate / Time Spent:** Ước lượng và thời gian thực tế làm việc (thường tính bằng giờ).
- **Story Points:** Đơn vị đo độ phức tạp/khối lượng công việc tương đối (không phải thời gian).

---

### 🧠 Câu hỏi thảo luận gợi mở

- Sự khác biệt chính giữa Task và Sub-task là gì? Khi nào bạn nên tạo Sub-task thay vì Task?
- Tại sao việc viết Description rõ ràng và đầy đủ lại quan trọng, đặc biệt là đối với Bug và User Story?
- Nếu một yêu cầu quá lớn để làm trong một Sprint, bạn nên tạo nó thành loại Issue nào? Tại sao?
- Theo bạn, trường thông tin nào là quan trọng nhất trên một Issue? Tại sao?

---

### 📌 Tài liệu & Tham khảo

- What is an issue? (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/what-is-an-issue/](https://support.atlassian.com/jira-software-cloud/docs/what-is-an-issue/)
- Các loại Issue mặc định (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/what-are-the-default-issue-types/](https://support.atlassian.com/jira-software-cloud/docs/what-are-the-default-issue-types/)
- Tạo Issue trong Jira (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/create-issues-and-sub-tasks/](https://support.atlassian.com/jira-software-cloud/docs/create-issues-and-sub-tasks/)
- Chỉnh sửa Issue trong Jira (Atlassian): [https://support.atlassian.com/jira-software-cloud/docs/edit-an-issue/](https://support.atlassian.com/jira-software-cloud/docs/edit-an-issue/)
