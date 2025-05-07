## 3. Pull Request là gì?

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được **Pull Request (PR)** là gì và vai trò của nó trong quy trình làm việc cộng tác với Git, đặc biệt khi sử dụng các nền tảng như GitHub, GitLab, Bitbucket.
- Nắm được những **lợi ích chính** của việc sử dụng Pull Request (Code Review, Thảo luận, Kiểm soát chất lượng).
- Hiểu được **quy trình cơ bản** của một Pull Request: tạo PR, review, thảo luận, merge PR.
- Biết cách một Pull Request có thể được **liên kết với các Issue trên Jira**.

---

### 🧩 Nội dung chi tiết

#### 3.1. Pull Request (PR) là gì?

**Pull Request (PR)** – hoặc **Merge Request (MR)** trên GitLab – là một tính năng của các nền tảng quản lý mã nguồn dựa trên Git (như GitHub, GitLab, Bitbucket). Nó không phải là một lệnh Git cốt lõi, mà là một cơ chế để **đề xuất và thảo luận về những thay đổi** bạn đã thực hiện trên một nhánh trước khi chúng được gộp (merge) vào một nhánh khác (thường là nhánh chính như `main` hoặc `develop`).

Hãy tưởng tượng bạn đã hoàn thành một tính năng mới trên nhánh `feature-login`. Thay vì tự mình gộp thẳng vào nhánh `main`, bạn tạo một Pull Request. Pull Request này thông báo cho những người khác trong nhóm rằng:

- "Tôi đã hoàn thành công việc trên nhánh `feature-login`."
- "Đây là những thay đổi tôi đã thực hiện (danh sách các commit)."
- "Làm ơn xem xét (review) những thay đổi này và cho tôi biết ý kiến."
- "Nếu mọi thứ ổn, hãy gộp (merge) những thay đổi này vào nhánh `main`."

Pull Request tạo ra một không gian để **thảo luận, đánh giá (code review)**, và thậm chí là **chạy các kiểm thử tự động** trước khi code mới được tích hợp.

#### 3.2. Lợi ích của việc sử dụng Pull Request

Sử dụng Pull Request mang lại nhiều lợi ích quan trọng cho quy trình phát triển phần mềm:

- **Code Review (Đánh giá mã nguồn):**
  - Đây là lợi ích lớn nhất. Các thành viên khác trong nhóm (hoặc người được chỉ định) có thể xem xét từng dòng code bạn đã thay đổi.
  - Họ có thể đưa ra nhận xét, đặt câu hỏi, gợi ý cải tiến, hoặc phát hiện lỗi tiềm ẩn.
  - Giúp cải thiện chất lượng code, chia sẻ kiến thức trong nhóm, và đảm bảo code tuân theo các tiêu chuẩn chung.
- **Thảo luận (Discussion):**
  - Pull Request cung cấp một nơi tập trung để thảo luận về các thay đổi cụ thể.
  - Mọi người có thể bình luận trực tiếp trên các dòng code, giúp cuộc trao đổi rõ ràng và dễ theo dõi.
- **Kiểm soát chất lượng (Quality Control):**
  - Trước khi merge, bạn có thể thiết lập các quy tắc, ví dụ: PR phải được ít nhất 2 người duyệt, hoặc phải vượt qua tất cả các bài kiểm thử tự động (CI/CD integration).
  - Giúp ngăn chặn việc đưa code lỗi hoặc chưa hoàn thiện vào nhánh chính.
- **Theo dõi lịch sử thay đổi rõ ràng hơn:**
  - Pull Request (sau khi được merge) thường trở thành một phần của lịch sử commit, ghi lại ai đã đề xuất thay đổi, ai review, và các cuộc thảo luận liên quan.
- **Tích hợp với các công cụ khác:**
  - Nhiều nền tảng cho phép tích hợp Pull Request với hệ thống CI/CD (Continuous Integration/Continuous Deployment) để tự động chạy build, test.
  - Có thể liên kết Pull Request với các Issue trên các công cụ quản lý dự án như Jira.

#### 3.3. Quy trình cơ bản của một Pull Request

Quy trình làm việc với Pull Request thường bao gồm các bước sau:

1.  **Tạo nhánh (Branch):** Bạn tạo một nhánh mới từ nhánh cơ sở (ví dụ: `main` hoặc `develop`) để làm việc trên một tính năng hoặc sửa lỗi.
    - `git checkout -b feature-new-button` (Tạo và chuyển sang nhánh mới)
2.  **Thực hiện thay đổi và Commit:** Bạn viết code, thực hiện các thay đổi cần thiết và commit chúng vào nhánh của mình.
    - `git add .`
    - `git commit -m "Add new button functionality"`
3.  **Đẩy nhánh lên Remote Repository (Push):** Bạn đẩy nhánh cục bộ của mình lên kho chứa từ xa.
    - `git push origin feature-new-button`
4.  **Tạo Pull Request:**
    - Truy cập nền tảng quản lý mã nguồn (GitHub, GitLab, Bitbucket).
    - Tìm đến repository của bạn.
    - Nền tảng thường sẽ tự động phát hiện nhánh mới được đẩy lên và gợi ý bạn tạo Pull Request. Hoặc bạn có thể vào mục "Pull Requests" (hoặc "Merge Requests") và nhấn nút "New Pull Request".
    - **Chọn nhánh nguồn (source branch):** Nhánh của bạn (`feature-new-button`).
    - **Chọn nhánh đích (target/base branch):** Nhánh bạn muốn gộp vào (ví dụ: `main`).
    - **Viết tiêu đề và mô tả cho Pull Request:** Tiêu đề nên tóm tắt thay đổi. Mô tả nên giải thích rõ hơn về những gì bạn đã làm, tại sao, và có thể liên kết đến Issue trên Jira (nếu có).
    - Nhấn "Create Pull Request".
5.  **Review và Thảo luận:**
    - Các thành viên khác trong nhóm (reviewers) sẽ nhận được thông báo về PR mới.
    - Họ xem xét code, có thể để lại bình luận, câu hỏi, hoặc yêu cầu thay đổi.
    - Bạn (người tạo PR) có thể trả lời bình luận, giải thích, hoặc thực hiện thêm các commit mới để cập nhật PR dựa trên phản hồi.
6.  **Merge Pull Request:**
    - Sau khi PR được duyệt (approved) và mọi vấn đề đã được giải quyết (nếu có), người có quyền (thường là chủ sở hữu repo hoặc reviewer) sẽ nhấn nút "Merge Pull Request".
    - Các thay đổi từ nhánh nguồn sẽ được gộp vào nhánh đích.
    - Thường có tùy chọn xóa nhánh nguồn sau khi merge.
7.  **Xóa nhánh (Tùy chọn):** Sau khi PR đã được merge, nhánh `feature-new-button` thường không còn cần thiết nữa và có thể được xóa cả ở local và remote để giữ cho repository gọn gàng.
    - `git branch -d feature-new-button` (Xóa nhánh local)
    - `git push origin --delete feature-new-button` (Xóa nhánh remote - nếu nền tảng không tự xóa)

#### 3.4. Liên kết Pull Request với Jira

Nhiều tổ chức sử dụng Jira để quản lý công việc và Git (thông qua GitHub, GitLab, Bitbucket) để quản lý mã nguồn. Việc liên kết giữa chúng rất quan trọng để có cái nhìn tổng thể về tiến độ.

**Cách thực hiện (thường là tự động hoặc bán tự động nếu tích hợp đúng cách):**

- **Nhắc đến Jira Issue ID trong Commit Message hoặc Tên Nhánh:**
  - Khi bạn commit, bạn có thể thêm ID của Jira Issue vào commit message. Ví dụ: `git commit -m "DEV-123: Fix login bug"`.
  - Hoặc đặt tên nhánh chứa Jira Issue ID: `git checkout -b DEV-123-fix-login-bug`.
- **Tự động liên kết khi tạo Pull Request:**
  - Nếu bạn đã tích hợp Jira với GitHub/GitLab/Bitbucket, khi bạn tạo Pull Request từ một nhánh có tên chứa Jira Issue ID (hoặc commit message chứa ID), nền tảng có thể tự động tạo liên kết giữa PR và Issue đó trên Jira.
  - Bạn cũng có thể thêm Jira Issue ID vào tiêu đề hoặc mô tả của Pull Request.

**Lợi ích của việc liên kết:**

- **Từ Jira Issue, bạn có thể thấy:**
  - Các commit liên quan.
  - Các nhánh đang được phát triển cho Issue đó.
  - Trạng thái của Pull Request (Open, Merged, Declined).
- **Từ Pull Request, bạn có thể dễ dàng truy cập:**
  - Thông tin chi tiết về yêu cầu hoặc lỗi trên Jira.
- Giúp Product Owner, Manager dễ dàng theo dõi tiến độ phát triển của một tính năng hoặc việc sửa lỗi từ Jira mà không cần phải vào trực tiếp GitHub/GitLab.
- Tự động chuyển trạng thái Jira Issue khi PR được merge (tùy cấu hình).

---

### 💬 Giải thích một số từ chuyên ngành trong phần này:

- **Pull Request (PR) / Merge Request (MR):** Đề xuất thay đổi code từ một nhánh này sang nhánh khác trên các nền tảng như GitHub, GitLab, Bitbucket, kèm theo cơ chế review và thảo luận.
- **Code Review:** Quá trình đánh giá, xem xét mã nguồn được viết bởi người khác để đảm bảo chất lượng, tìm lỗi, và chia sẻ kiến thức.
- **Source Branch (Nhánh nguồn):** Nhánh chứa các thay đổi bạn muốn gộp.
- **Target/Base Branch (Nhánh đích):** Nhánh mà bạn muốn gộp các thay đổi vào.
- **Reviewer:** Người được giao nhiệm vụ xem xét và đánh giá Pull Request.
- **Approve (Duyệt):** Hành động chấp thuận các thay đổi trong Pull Request.
- **CI/CD (Continuous Integration/Continuous Deployment):** Các thực hành tự động hóa quá trình build, test, và triển khai phần mềm.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Theo bạn, tại sao Code Review lại quan trọng trong quy trình Pull Request?
- Nếu bạn là người review một Pull Request, bạn sẽ chú ý đến những điểm gì trong code?
- Lợi ích của việc liên kết Pull Request với Jira Issue là gì từ góc độ của một Project Manager?
- Bạn nghĩ sao về việc tự động xóa nhánh sau khi Pull Request đã được merge?

---

### 📌 Tài liệu & Tham khảo

- GitHub Docs - About Pull Requests: [https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- GitLab Docs - Merge Requests: [https://docs.gitlab.com/ee/user/project/merge_requests/](https://docs.gitlab.com/ee/user/project/merge_requests/)
- Atlassian Bitbucket Docs - Learn about Pull Requests: [https://support.atlassian.com/bitbucket-cloud/docs/learn-about-pull-requests/](https://support.atlassian.com/bitbucket-cloud/docs/learn-about-pull-requests/)
- Integrating Jira with Bitbucket Cloud: [https://support.atlassian.com/jira-cloud-administration/docs/integrate-jira-cloud-with-bitbucket-cloud/](https://support.atlassian.com/jira-cloud-administration/docs/integrate-jira-cloud-with-bitbucket-cloud/)
