# 2. Hỗ trợ viết User Story, Test Case, Tóm tắt tài liệu

## 📋 Tổng quan

Một trong những ứng dụng hữu ích nhất của AI trong quản trị dự án phần mềm là hỗ trợ tạo và cải thiện các tài liệu dự án như User Story, Test Case và tóm tắt tài liệu. Module này sẽ hướng dẫn cách khai thác sức mạnh của AI để tạo ra các tài liệu đạt tiêu chuẩn cao, tiết kiệm thời gian và nâng cao chất lượng dự án.

## 🎯 Mục tiêu

- Biết cách sử dụng AI để viết User Story đạt chuẩn INVEST
- Tạo Test Case cơ bản và nâng cao với sự hỗ trợ của AI
- Sử dụng AI để tóm tắt tài liệu dài thành các điểm chính
- Hiểu cách chuyển đổi ý tưởng thô thành đặc tả kỹ thuật có cấu trúc
- Đánh giá và cải thiện chất lượng nội dung do AI tạo ra

## 📚 Nội dung chi tiết

### 1. Sử dụng AI để viết User Story đạt chuẩn INVEST

#### Chuẩn INVEST cho User Story

INVEST là một bộ tiêu chí để đánh giá chất lượng của một User Story:

- **I** - Independent (Độc lập): Không phụ thuộc vào các story khác
- **N** - Negotiable (Có thể thương lượng): Chi tiết có thể thảo luận
- **V** - Valuable (Có giá trị): Mang lại giá trị cho người dùng/khách hàng
- **E** - Estimable (Có thể ước lượng): Team có thể ước tính công sức cần thiết
- **S** - Small (Nhỏ gọn): Đủ nhỏ để có thể hoàn thành trong một sprint
- **T** - Testable (Có thể kiểm thử): Có tiêu chí chấp nhận rõ ràng

#### Cấu trúc User Story chuẩn

```
As a [role]
I want to [capability]
So that [benefit]

Acceptance Criteria:
1. Given [context], when [action], then [expected result]
2. Given [context], when [action], then [expected result]
...
```

#### Sử dụng ChatGPT/Gemini/Claude để viết User Story

**Prompt mẫu cơ bản:**

```
Viết một User Story theo chuẩn INVEST cho một tính năng [mô tả tính năng] trong ứng dụng [loại ứng dụng].
Bao gồm cả các tiêu chí chấp nhận theo định dạng Given-When-Then.
```

**Prompt mẫu nâng cao:**

```
Tôi cần viết một User Story theo chuẩn INVEST cho một tính năng mới trong ứng dụng quản lý dự án của chúng tôi.

Chi tiết tính năng:
- Người dùng là Project Manager
- Tính năng là tạo báo cáo tự động về tiến độ sprint hiện tại
- Báo cáo cần hiển thị các task hoàn thành, đang thực hiện, và tồn đọng
- Báo cáo có thể xuất ra PDF hoặc chia sẻ qua email

Hãy giúp tôi:
1. Viết User Story theo cấu trúc "As a..., I want to..., So that..."
2. Đưa ra 3-5 tiêu chí chấp nhận theo định dạng "Given..., When..., Then..."
3. Đánh giá xem User Story này có đáp ứng các tiêu chí INVEST không và cách cải thiện nếu cần
```

#### Ví dụ kết quả AI tạo ra

```
As a Project Manager
I want to generate automated reports on current sprint progress
So that I can quickly share status updates with stakeholders and identify potential issues early

Acceptance Criteria:
1. Given I am on the sprint dashboard, when I click "Generate Report", then the system should create a report showing all tasks categorized as completed, in-progress, and backlogged
2. Given a report has been generated, when I select "Export as PDF", then the report should be downloaded in PDF format
3. Given a report has been generated, when I select "Share via Email" and enter recipient emails, then the system should send the report to those recipients
4. Given I am viewing a generated report, when I hover over any task status section, then I should see a percentage completion and time remaining
5. Given a new task status is updated in the sprint, when I regenerate the report, then it should reflect the most recent changes
```

#### Cách tùy chỉnh và cải thiện User Story do AI tạo ra

- Điều chỉnh phạm vi nếu User Story quá lớn
- Làm rõ giá trị mang lại cho người dùng
- Thêm chi tiết vào tiêu chí chấp nhận nếu cần
- Đảm bảo ngôn ngữ rõ ràng và nhất quán

### 2. Tạo và cải thiện Test Case với AI

#### Cấu trúc Test Case tiêu chuẩn

- **ID**: Định danh duy nhất của test case
- **Title**: Tiêu đề ngắn gọn
- **Description**: Mô tả mục đích của test case
- **Preconditions**: Điều kiện tiên quyết trước khi thực hiện
- **Test Steps**: Các bước thực hiện chi tiết
- **Expected Results**: Kết quả mong đợi cho mỗi bước
- **Test Data**: Dữ liệu kiểm thử cần thiết
- **Status**: Trạng thái của test case (Draft, Ready, Passed, Failed)
- **Notes**: Ghi chú bổ sung (nếu có)

#### Prompt mẫu cho việc tạo Test Case

```
Hãy tạo một bộ Test Case đầy đủ cho User Story sau:

[Copy User Story vừa tạo]

Mỗi test case cần có:
1. ID và tiêu đề
2. Mô tả mục đích
3. Điều kiện tiên quyết
4. Các bước kiểm thử chi tiết
5. Kết quả mong đợi cho mỗi bước
6. Dữ liệu kiểm thử cần thiết

Hãy bao gồm cả test case cho luồng xử lý chính và các trường hợp ngoại lệ.
```

#### Các loại Test Case cần yêu cầu AI tạo

- **Positive Testing**: Kiểm tra tính năng hoạt động đúng với input hợp lệ
- **Negative Testing**: Kiểm tra phản ứng với input không hợp lệ
- **Edge Cases**: Kiểm tra với giá trị biên
- **Performance Testing**: Kiểm tra hiệu suất trong điều kiện cụ thể
- **UI/UX Testing**: Kiểm tra giao diện và trải nghiệm người dùng

### 3. Tóm tắt tài liệu yêu cầu dài

#### Kỹ thuật yêu cầu AI tóm tắt hiệu quả

- **Xác định mục tiêu tóm tắt**: Đặt câu hỏi cụ thể về thông tin cần trích xuất
- **Chọn độ chi tiết phù hợp**: Chỉ định độ dài hoặc mức độ chi tiết mong muốn
- **Định dạng đầu ra**: Yêu cầu định dạng cụ thể (bullet points, headings, table)
- **Trọng tâm**: Chỉ định khía cạnh cần tập trung (kỹ thuật, kinh doanh, v.v.)

#### Prompt mẫu cho việc tóm tắt tài liệu

```
Tôi cần tóm tắt tài liệu đặc tả yêu cầu dài này thành một bản tóm tắt ngắn gọn dành cho team phát triển.
Tập trung vào:
1. Các yêu cầu chức năng chính
2. Ràng buộc kỹ thuật quan trọng
3. Điểm cần lưu ý trong triển khai

Hãy định dạng kết quả với các tiêu đề rõ ràng và danh sách đánh dấu. Giới hạn trong khoảng 1-2 trang.

Đây là tài liệu:
[Dán nội dung tài liệu cần tóm tắt]
```

### 4. Biến ý tưởng thô thành đặc tả kỹ thuật có cấu trúc

#### Cấu trúc đặc tả kỹ thuật cơ bản

- **Tổng quan**: Mô tả ngắn gọn về tính năng/giải pháp
- **Mục tiêu**: Vấn đề cần giải quyết và mục tiêu cần đạt được
- **Chi tiết thiết kế**: Giải thích cách tiếp cận kỹ thuật
  - Kiến trúc hệ thống
  - Database schema (nếu có)
  - API endpoints (nếu có)
  - UI mockups (nếu có)
- **Dòng xử lý**: Luồng xử lý trong hệ thống
- **Giới hạn và ràng buộc**: Các hạn chế và yêu cầu đặc biệt
- **Các vấn đề cần xem xét**: Những điểm cần lưu ý hoặc thảo luận thêm

#### Prompt mẫu cho việc tạo đặc tả kỹ thuật

```
Tôi có một ý tưởng thô cho tính năng mới và cần chuyển thành đặc tả kỹ thuật có cấu trúc:

Ý tưởng: [Mô tả ý tưởng ban đầu]

Công nghệ hiện có của dự án:
- Backend: [công nghệ backend]
- Frontend: [công nghệ frontend]
- Database: [loại database]
- Infrastructure: [thông tin về hạ tầng]

Hãy giúp tôi tạo đặc tả kỹ thuật đầy đủ với:
1. Tổng quan và mục tiêu
2. Chi tiết thiết kế và kiến trúc đề xuất
3. Dòng xử lý chính
4. API endpoints (nếu cần)
5. Database schema changes (nếu cần)
6. Các vấn đề cần xem xét và giới hạn
```

### 5. Kiểm tra chất lượng nội dung được tạo bởi AI

#### Các tiêu chí đánh giá

1. **Tính nhất quán**: Nội dung có mâu thuẫn nội tại không?
2. **Tính đầy đủ**: Đã bao gồm tất cả các khía cạnh cần thiết chưa?
3. **Tính khả thi**: Giải pháp đề xuất có khả thi về mặt kỹ thuật không?
4. **Tính phù hợp**: Phù hợp với bối cảnh dự án và công nghệ hiện có?
5. **Tính rõ ràng**: Ngôn ngữ và thuật ngữ có dễ hiểu không?

#### Prompt để yêu cầu AI tự đánh giá nội dung

```
Hãy đánh giá nội dung [User Story/Test Case/Đặc tả kỹ thuật] vừa tạo ra dựa trên các tiêu chí sau:

1. Tính nhất quán: Có điểm mâu thuẫn nào không?
2. Tính đầy đủ: Đã bao gồm mọi khía cạnh cần thiết chưa?
3. Tính khả thi: Mọi thứ đề xuất có thực hiện được không?
4. Tính phù hợp: Phù hợp với bối cảnh dự án không?
5. Tính rõ ràng: Ngôn ngữ có rõ ràng, dễ hiểu không?

Đề xuất cải thiện cụ thể cho mỗi vấn đề phát hiện được.
```

#### Điểm cần lưu ý khi sử dụng AI

- **Kiểm tra lỗi kiến thức**: AI có thể đưa ra thông tin không chính xác về công nghệ
- **Bối cảnh dự án**: AI không biết đầy đủ về bối cảnh, hạn chế, quy trình của dự án
- **Audit con người**: Luôn có người kiểm tra lại nội dung do AI tạo ra
- **Nhất quán với quy trình**: Đảm bảo nội dung phù hợp với quy trình của dự án
- **Tính bảo mật**: Cân nhắc khi chia sẻ thông tin nhạy cảm với AI

## 💡 Các kỹ thuật nâng cao

### Iterative Refinement (Tinh chỉnh lặp lại)

1. Tạo phiên bản đầu tiên với AI
2. Yêu cầu AI đánh giá và chỉ ra điểm yếu
3. Yêu cầu AI cải thiện những điểm yếu đó
4. Lặp lại quy trình cho đến khi đạt chất lượng mong muốn

### Chain-of-Thought Prompting

Yêu cầu AI giải thích lý do đằng sau mỗi quyết định và đề xuất trong nội dung tạo ra:

```
Hãy thiết kế Test Case cho tính năng XYZ, và giải thích lý do bạn chọn từng test case cụ thể. Đặc biệt giải thích tại sao các edge case được chọn lại quan trọng.
```

### Hybrid Approach (Phương pháp kết hợp)

1. Người dùng cung cấp cấu trúc và hướng dẫn ban đầu
2. AI tạo nội dung dựa trên hướng dẫn
3. Người dùng chỉnh sửa và yêu cầu AI tinh chỉnh các phần cụ thể

## ⚡ Thực hành

### Bài tập 1: Viết User Story với AI

1. Chọn một tính năng đơn giản (ví dụ: tính năng đăng nhập bằng mạng xã hội)
2. Sử dụng các prompt mẫu để yêu cầu AI tạo User Story
3. Đánh giá dựa trên tiêu chí INVEST
4. Tinh chỉnh prompt và yêu cầu AI tạo lại

### Bài tập 2: Tóm tắt tài liệu với AI

1. Chọn một tài liệu dự án dài (ví dụ: đặc tả yêu cầu, tài liệu kỹ thuật)
2. Yêu cầu AI tóm tắt tài liệu theo nhiều cách khác nhau:
   - Tóm tắt cho nhóm kỹ thuật
   - Tóm tắt cho quản lý
   - Tóm tắt dạng bullet points ngắn gọn
3. So sánh các kết quả và đánh giá hiệu quả của các prompt khác nhau

## 📚 Tài liệu tham khảo

1. [Writing Effective User Stories in Agile](https://www.mountaingoatsoftware.com/agile/user-stories)
2. [Test Case Writing Best Practices](https://www.guru99.com/test-case.html)
3. [Technical Documentation Best Practices](https://docs.microsoft.com/en-us/style-guide/welcome/)
4. [INVEST in Good Stories, and SMART Tasks](https://xp123.com/articles/invest-in-good-stories-and-smart-tasks/)
5. [AI-Assisted Technical Writing Guide](https://www.forbes.com/sites/forbestechcouncil/2023/03/15/how-ai-is-transforming-technical-documentation/)
