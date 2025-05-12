# 4. Thực hành viết prompt cho QTDDA

## 📋 Tổng quan

Sau khi đã nắm vững các nguyên lý và kỹ thuật prompt engineering, việc áp dụng chúng vào các tình huống cụ thể trong quản trị dự án phát triển phần mềm (QTDDA) sẽ giúp tối ưu hóa hiệu quả công việc. Module này tập trung vào việc thực hành viết prompt cho các tác vụ phổ biến trong quy trình quản lý dự án, từ phân tích yêu cầu, ước lượng thời gian, lập kế hoạch sprint đến viết tài liệu kỹ thuật và báo cáo tiến độ. Mỗi phần đều cung cấp prompt mẫu, giải thích lý do và hướng dẫn điều chỉnh theo nhu cầu cụ thể của dự án.

## 🎯 Mục tiêu

- Nắm vững cách áp dụng prompt engineering vào các tác vụ QTDDA hàng ngày
- Xây dựng bộ sưu tập prompt hiệu quả cho từng giai đoạn của dự án phần mềm
- Thực hành viết và điều chỉnh prompt cho các tình huống thực tế
- Đánh giá hiệu quả của các prompt và liên tục cải thiện

## 📚 Nội dung chi tiết

### 1. Prompt cho phân tích yêu cầu và tạo User Story

#### Phân tích yêu cầu từ mô tả thô

**Tình huống**: Bạn nhận được một mô tả yêu cầu không rõ ràng từ khách hàng và cần phân tích để tạo các yêu cầu có cấu trúc.

**Prompt mẫu**:

```
Với vai trò là một Business Analyst có kinh nghiệm, hãy phân tích yêu cầu thô dưới đây và chuyển thành các yêu cầu chức năng có cấu trúc.

Yêu cầu thô từ khách hàng:
"""
[Dán yêu cầu thô từ khách hàng vào đây]
"""

Hãy cung cấp kết quả phân tích theo cấu trúc sau:
1. Tóm tắt tổng quan về tính năng/hệ thống (2-3 câu)
2. Danh sách các yêu cầu chức năng chính (FR), mỗi yêu cầu có:
   - ID (FR-XX)
   - Mô tả ngắn gọn, rõ ràng
   - Mức độ ưu tiên (Cao/Trung bình/Thấp)
   - Phụ thuộc (nếu có)
3. Danh sách các yêu cầu phi chức năng (NFR) liên quan
4. Các câu hỏi làm rõ (nếu có điểm nào chưa rõ trong yêu cầu gốc)
5. Đề xuất các test cases cơ bản để xác nhận tính năng

Lưu ý: Hãy đảm bảo yêu cầu rõ ràng, đo lường được và khả thi.
```

**Lý do hiệu quả**:

- Gán vai trò cụ thể (Business Analyst có kinh nghiệm)
- Định nghĩa rõ đầu vào (yêu cầu thô) và đầu ra mong muốn (cấu trúc FR/NFR)
- Cung cấp hướng dẫn về format và nội dung cần bao gồm
- Yêu cầu không chỉ phân tích mà còn xác định các điểm chưa rõ và đề xuất test cases

#### Chuyển đổi yêu cầu thành User Stories đạt chuẩn INVEST

**Prompt mẫu**:

```
Hãy chuyển đổi các yêu cầu chức năng dưới đây thành User Stories theo chuẩn INVEST (Independent, Negotiable, Valuable, Estimable, Small, Testable).

Yêu cầu chức năng:
"""
[Danh sách các yêu cầu chức năng]
"""

Cho mỗi User Story, hãy cung cấp:
1. Format "As a [role], I want [capability], so that [benefit]"
2. 3-5 tiêu chí chấp nhận theo format "Given [context], When [action], Then [expected result]"
3. Đánh giá ngắn gọn về việc User Story đáp ứng các tiêu chí INVEST
4. Story Points ước lượng (thang điểm Fibonacci: 1, 2, 3, 5, 8, 13) và lý do

Nếu một yêu cầu chức năng quá lớn, hãy chia thành nhiều User Stories nhỏ hơn.

Lưu ý: Đảm bảo mỗi User Story đều mang lại giá trị kinh doanh cụ thể và có thể triển khai độc lập.
```

**Ví dụ kết quả**:

```
Từ yêu cầu chức năng: "Người dùng có thể đặt lại mật khẩu khi quên"

User Story:
- ID: US-01
- Title: Password Reset Functionality
- Story: As a registered user, I want to reset my password when I forget it, so that I can regain access to my account without contacting support.

Acceptance Criteria:
1. Given I am on the login page, when I click on "Forgot Password", then I should be redirected to the password reset page.
2. Given I am on the password reset page, when I enter my registered email and submit, then I should receive a password reset link.
3. Given I have received the reset link, when I click on it, then I should be able to enter a new password.
4. Given I am on the reset password form, when I enter a new password that meets the security requirements, then my password should be updated.
5. Given I have reset my password, when I try to login with the new password, then I should gain access to my account.

INVEST Assessment:
- Independent: Yes, can be implemented separately from other features
- Negotiable: Yes, details like email template can be adjusted
- Valuable: Yes, provides clear user benefit
- Estimable: Yes, clear scope and requirements
- Small: Yes, focused on a single functionality
- Testable: Yes, has clear acceptance criteria

Story Points: 3 - This is a standard functionality with established patterns, requiring frontend and backend work but no complex logic.
```

### 2. Prompt cho việc ước lượng thời gian và độ phức tạp

#### Ước lượng Story Points cho User Stories

**Prompt mẫu**:

```
Với vai trò là Scrum Master có kinh nghiệm, hãy giúp tôi ước lượng Story Points cho các User Stories sau đây. Tôi đang sử dụng thang điểm Fibonacci (1, 2, 3, 5, 8, 13, 21) với các mức độ phức tạp sau:

- 1 point: Rất đơn giản, chỉ thay đổi text/style
- 2 points: Đơn giản, thay đổi nhỏ trong UI hoặc logic
- 3 points: Trung bình, cần thay đổi frontend và backend nhỏ
- 5 points: Phức tạp vừa, cần thay đổi đáng kể và có thể ảnh hưởng đến nhiều thành phần
- 8 points: Phức tạp cao, tính năng mới hoàn toàn
- 13 points: Rất phức tạp, cần refactor lớn hoặc tích hợp với hệ thống bên ngoài
- 21 points: Cực kỳ phức tạp, có thể cần chia nhỏ hơn

Thông tin về team và dự án:
- Tech stack: [liệt kê tech stack]
- Team experience: [mức độ kinh nghiệm của team]
- Sprint length: [độ dài sprint]
- Velocity trung bình hiện tại: [số điểm]

User Stories cần ước lượng:
"""
[Danh sách User Stories]
"""

Cho mỗi User Story, hãy cung cấp:
1. Ước lượng Story Points
2. Lý do chi tiết cho ước lượng này (phân tích độ phức tạp kỹ thuật, UI/UX, testing, rủi ro)
3. Breakdown công việc ước lượng cần làm (frontend, backend, testing, etc.)
4. Đề xuất cách chia nhỏ (nếu > 8 points)
```

#### Planning Poker Facilitation

**Prompt mẫu**:

```
Tôi cần tiến hành một buổi Planning Poker với team để ước lượng User Stories. Hãy đóng vai trò Scrum Master điều phối buổi Planning Poker theo kịch bản sau:

User Story hiện tại: [Copy User Story]

Hãy giả lập một buổi Planning Poker với 5 thành viên team (2 frontend devs, 2 backend devs, 1 QA) theo các bước sau:

1. Giới thiệu User Story và giải thích ngắn gọn
2. Xác định các câu hỏi làm rõ mà team có thể đặt và cách bạn sẽ trả lời
3. Mô phỏng quá trình ước lượng từng thành viên với lý do (giả lập 1 vòng với kết quả khác nhau)
4. Hướng dẫn thảo luận khi có sự khác biệt lớn trong ước lượng
5. Mô phỏng vòng ước lượng thứ hai sau thảo luận
6. Kết luận với Story Points cuối cùng

Mục tiêu là có được một kịch bản thực tế về cách điều phối buổi Planning Poker hiệu quả, với các kỹ thuật đặt câu hỏi và điều hướng thảo luận để đạt được consensus.
```

### 3. Prompt cho việc lập kế hoạch Sprint

#### Chuẩn bị cho Sprint Planning

**Prompt mẫu**:

```
Với vai trò là Scrum Master, hãy giúp tôi chuẩn bị cho buổi Sprint Planning sắp tới với thông tin sau:

Thông tin Sprint:
- Sprint số: [số thứ tự]
- Thời gian: [thời lượng] (từ [ngày bắt đầu] đến [ngày kết thúc])
- Team capacity: [số giờ available] (sau khi trừ meetings, PTO, etc.)
- Velocity trung bình: [số Story Points]

Product Backlog hiện tại (đã được sắp xếp theo ưu tiên):
"""
[Danh sách User Stories trong backlog]
"""

Hãy giúp tôi:
1. Đề xuất Sprint Goal phù hợp dựa trên các User Stories ưu tiên cao
2. Chọn các User Stories nên đưa vào Sprint Backlog (dựa trên velocity, dependencies, và balance giữa các loại công việc)
3. Danh sách các rủi ro tiềm ẩn cần thảo luận trong Sprint Planning
4. Cấu trúc chi tiết cho buổi Sprint Planning (agenda và timeboxing)
5. Các câu hỏi quan trọng cần đặt ra trong buổi họp
6. Chiến lược để đảm bảo commitment từ team

Lưu ý: Đảm bảo Sprint Goal SMART (Specific, Measurable, Achievable, Relevant, Time-bound) và sprint có workload cân bằng.
```

#### Lập Sprint Retrospective

**Prompt mẫu**:

```
Hãy giúp tôi chuẩn bị và điều phối một buổi Sprint Retrospective hiệu quả cho team Scrum. Thông tin về Sprint vừa kết thúc:

- Sprint số: [số thứ tự]
- Kết quả: [hoàn thành x/y Story Points]
- Những thành công chính: [liệt kê]
- Những thách thức: [liệt kê]
- Các action items từ Retrospective trước: [liệt kê và trạng thái]

Hãy cung cấp:
1. Format Retrospective phù hợp cho team 7-8 người làm việc từ xa (sử dụng [tools])
2. Agenda chi tiết với timeboxing
3. 3-4 hoạt động tương tác (icebreaker, retrospective activities) cụ thể với hướng dẫn chi tiết
4. Các câu hỏi mở hiệu quả để thúc đẩy thảo luận chân thật
5. Phương pháp nhóm feedback thành themes và đưa ra action items
6. Template để theo dõi action items từ buổi Retrospective

Lưu ý: Tập trung vào môi trường an toàn tâm lý, tránh đổ lỗi, và đảm bảo mọi người đều có cơ hội chia sẻ ý kiến.
```

### 4. Prompt cho việc viết tài liệu kỹ thuật

#### Tạo tài liệu thiết kế kỹ thuật

**Prompt mẫu**:

```
Tôi cần tạo một tài liệu thiết kế kỹ thuật (Technical Design Document) cho tính năng sau đây. Hãy giúp tôi xây dựng tài liệu với cấu trúc chuyên nghiệp.

Tính năng: [Mô tả ngắn gọn về tính năng]

Thông tin dự án:
- Tech stack: [liệt kê công nghệ]
- Kiến trúc hiện tại: [mô tả ngắn gọn]
- Các ràng buộc kỹ thuật: [nếu có]
- Yêu cầu phi chức năng: [performance, security, scalability, etc.]

Hãy tạo tài liệu thiết kế kỹ thuật bao gồm:

1. Tổng quan (Overview)
   - Mục đích của tính năng
   - Phạm vi thiết kế
   - Assumptions và Constraints

2. Thiết kế kiến trúc (Architectural Design)
   - High-level architecture diagram
   - Components và interactions
   - Data flow

3. Thiết kế Database
   - Schema changes (nếu có)
   - New tables/fields
   - Migrations plan

4. API Design
   - Endpoints mới/thay đổi
   - Request/Response formats
   - Error handling

5. Frontend Changes
   - UI components
   - State management
   - User flows

6. Xem xét Security
   - Authentication/Authorization concerns
   - Data protection
   - Input validation

7. Test Strategy
   - Unit tests approach
   - Integration tests
   - Performance testing requirements

8. Deployment Plan
   - Dependencies
   - Rollout strategy
   - Rollback plan

9. Các vấn đề cần xem xét và rủi ro tiềm ẩn

Hãy sử dụng pseudocode, diagrams mô tả (bằng text), và technical language phù hợp với senior developers.
```

#### Viết tài liệu hướng dẫn sử dụng (User Documentation)

**Prompt mẫu**:

```
Tôi cần tạo tài liệu hướng dẫn người dùng cho tính năng [tên tính năng] trong [tên sản phẩm]. Đối tượng người dùng là [mô tả đối tượng người dùng: technical level, roles, etc.].

Hãy giúp tôi tạo một tài liệu hướng dẫn người dùng rõ ràng, dễ hiểu với các phần sau:

1. Giới thiệu tính năng
   - Mục đích và lợi ích
   - Khi nào nên sử dụng

2. Cách truy cập và kích hoạt tính năng
   - Vị trí trong UI
   - Quyền cần thiết

3. Hướng dẫn từng bước (step-by-step guide)
   - Mỗi bước với mô tả rõ ràng (mô tả như thể có hình ảnh minh họa)
   - Tips và best practices cho mỗi bước

4. Các tình huống sử dụng phổ biến (use cases)
   - Scenario 1: [mô tả]
   - Scenario 2: [mô tả]
   - (2-3 use cases phổ biến nhất)

5. Troubleshooting phổ biến
   - Vấn đề 1: [mô tả vấn đề] → Giải pháp: [mô tả giải pháp]
   - Vấn đề 2: [mô tả vấn đề] → Giải pháp: [mô tả giải pháp]

6. FAQ (5-7 câu hỏi thường gặp và câu trả lời)

7. Resources liên quan và hỗ trợ
   - Liên kết đến tài liệu liên quan
   - Cách nhận hỗ trợ thêm

Yêu cầu về style:
- Sử dụng ngôn ngữ đơn giản, tránh jargon kỹ thuật (hoặc giải thích nếu cần thiết)
- Câu ngắn gọn, rõ ràng
- Sử dụng bullet points và numbered lists
- Highlight các keywords và actions
- Viết hướng dẫn ở dạng imperative voice (Click..., Enter..., Select...)
```

### 5. Prompt cho phân tích và báo cáo tiến độ dự án

#### Tạo Status Report hàng tuần

**Prompt mẫu**:

```
Giúp tôi tạo một Weekly Project Status Report chuyên nghiệp dựa trên thông tin dưới đây. Report này sẽ được chia sẻ với stakeholders và management.

Thông tin dự án:
- Tên dự án: [tên]
- Sprint hiện tại: [số/tên]
- Thời gian report: Week ending [ngày]

Metrics:
- Planned Story Points: [số]
- Completed Story Points: [số]
- Burndown Chart: [mô tả tình trạng: ahead, behind, on track]
- Bugs: [số mới]/[số đã fix]/[số tồn đọng]
- Test Coverage: [%]

Accomplishments tuần này:
- [bullet point 1]
- [bullet point 2]
- [bullet point 3]

Planned cho tuần tới:
- [bullet point 1]
- [bullet point 2]
- [bullet point 3]

Blockers & Issues:
- [mô tả issue 1 + status/mitigation]
- [mô tả issue 2 + status/mitigation]

Risks:
- [mô tả risk 1 + mitigation plan]
- [mô tả risk 2 + mitigation plan]

Hãy tạo một report chuyên nghiệp, ngắn gọn (1 trang) nhưng đầy đủ thông tin, với:
1. Executive Summary ngắn gọn ở đầu (2-3 câu tóm tắt tình trạng)
2. Visual indicators (🟢 Green/🟡 Yellow/🔴 Red) cho các section chính
3. Callouts cho các điểm cần chú ý đặc biệt
4. Next steps và action items rõ ràng
5. Format markdown để dễ đọc

Sử dụng ngôn ngữ chuyên nghiệp, khách quan, và facts-based.
```

#### Phân tích dữ liệu từ Jira/Git

**Prompt mẫu**:

```
Hãy phân tích dữ liệu project metrics dưới đây và tạo một báo cáo insights về hiệu suất team và dự án. Dữ liệu được export từ Jira và Git trong 3 sprints gần nhất.

Sprint metrics:
```

[Sprint 5]

- Duration: 2 weeks (May 1-14)
- Committed: 45 story points
- Completed: 38 story points
- Carryover: 7 story points
- New bugs reported: 8
- Bugs resolved: 12
- Average time in code review: 1.2 days
- Team capacity: 90% (1 PTO)

[Sprint 6]

- Duration: 2 weeks (May 15-28)
- Committed: 40 story points
- Completed: 35 story points
- Carryover: 5 story points
- New bugs reported: 5
- Bugs resolved: 8
- Average time in code review: 1.5 days
- Team capacity: 100%

[Sprint 7]

- Duration: 2 weeks (May 29-Jun 11)
- Committed: 42 story points
- Completed: 32 story points
- Carryover: 10 story points
- New bugs reported: 12
- Bugs resolved: 7
- Average time in code review: 1.8 days
- Team capacity: 80% (1 sick leave + training)

```

Commit data:
```

- Sprint 5: 58 commits (18 frontend, 35 backend, 5 infrastructure)
- Sprint 6: 62 commits (25 frontend, 32 backend, 5 infrastructure)
- Sprint 7: 47 commits (20 frontend, 22 backend, 5 infrastructure)

```

Hãy phân tích dữ liệu này và cung cấp:
1. Executive Summary về hiệu suất team (1 đoạn)
2. Trend analysis với các observations chính
3. 3-5 key insights, bao gồm cả positive points và areas for improvement
4. Potential bottlenecks và root causes
5. 3-4 actionable recommendations cụ thể để cải thiện hiệu suất
6. Velocity forecast cho 2 sprints tiếp theo với confidence level

Hãy sử dụng phương pháp phân tích dữ liệu định lượng kết hợp với kinh nghiệm quản lý dự án Agile để đưa ra insights sâu sắc và thực tế.
```

### 6. Prompt cho việc tìm giải pháp khi gặp vấn đề trong dự án

#### Phân tích nguyên nhân gốc rễ (Root Cause Analysis)

**Prompt mẫu**:

```
Hãy tiến hành phân tích nguyên nhân gốc rễ (RCA - Root Cause Analysis) cho vấn đề dự án sau:

Mô tả vấn đề:
"""
[Chi tiết mô tả vấn đề đang gặp phải trong dự án]
"""

Thông tin bối cảnh:
- Timeline của vấn đề: [khi nào phát hiện, diễn biến]
- Impact: [ảnh hưởng đến dự án, người dùng, business]
- Các biện pháp tạm thời đã áp dụng: [nếu có]
- Thông tin liên quan khác: [team structure, processes, tools]

Hãy tiến hành RCA với phương pháp 5 Whys kết hợp Fishbone (Ishikawa) diagram, phân tích các khía cạnh:
1. People (liên quan đến con người)
2. Process (quy trình làm việc)
3. Technology (công nghệ, tools)
4. Environment (môi trường làm việc)
5. Management (quản lý)

Cho mỗi khía cạnh:
- Xác định các potential causes
- Áp dụng 5 Whys để đi sâu đến root cause
- Đánh giá mức độ ảnh hưởng của từng cause (High/Medium/Low)

Cuối cùng:
1. Xác định 1-3 root causes chính với mức độ confidence
2. Đề xuất các biện pháp khắc phục ngắn hạn
3. Đề xuất các biện pháp phòng ngừa dài hạn
4. Metrics để theo dõi hiệu quả của giải pháp
```

#### Giải quyết xung đột trong team

**Prompt mẫu**:

```
Với vai trò là Scrum Master có kinh nghiệm, hãy tư vấn cách giải quyết tình huống xung đột trong team dưới đây:

Tình huống:
"""
[Mô tả chi tiết về tình huống xung đột đang xảy ra]
"""

Bối cảnh team:
- Team composition: [số lượng thành viên, roles, seniority]
- Team history: [thời gian làm việc cùng nhau, dynamic trước đây]
- Văn hóa làm việc: [remote/hybrid/onsite, collaboration style]

Hãy phân tích tình huống này và cung cấp:
1. Đánh giá loại xung đột (task-based, process-based, relationship-based, technical disagreement)
2. Các perspective khách quan từ các bên liên quan
3. 3-5 approach khác nhau để giải quyết, với pros/cons của từng approach
4. Kế hoạch hành động chi tiết cho phương án được đề xuất, bao gồm:
   - Chuẩn bị trước các cuộc họp cần thiết
   - Script/talking points cho các cuộc trò chuyện khó khăn
   - Follow-up actions để đảm bảo giải quyết triệt để
5. Chiến lược dài hạn để phòng ngừa các xung đột tương tự

Lưu ý: Đảm bảo đề xuất đặt team health lên hàng đầu, xây dựng psychological safety, và tuân thủ Agile values & principles.
```

## 💡 Kỹ thuật nâng cao

### 1. Template hóa Prompt theo quy trình dự án

Tạo bộ template prompt cho từng giai đoạn của dự án:

1. **Inception Phase**

```
[PROJECT INCEPTION PROMPT]
Hãy giúp tôi tạo artifacts cho phase khởi động dự án [tên dự án] với thông tin sau:

Mô tả dự án: [mô tả ngắn gọn]
Stakeholders chính: [danh sách]
Timeline dự kiến: [timeline]
Business objectives: [danh sách mục tiêu]

Hãy tạo các artifacts sau:
1. Project Vision Statement (1 đoạn ngắn gọn)
2. High-level Roadmap (4-6 milestones chính)
3. Initial Risk Assessment (top 5 risks)
4. RACI Matrix cho các stakeholders
5. Success Metrics (3-5 KPIs chính)

Sử dụng format markdown, ngắn gọn nhưng đầy đủ thông tin cần thiết.
```

2. **Planning Phase**
3. **Execution Phase**
4. **Monitoring Phase**
5. **Closing Phase**

### 2. Meta-prompting cho tự động cải thiện prompt

Sử dụng AI để tự cải thiện prompt của bạn:

```
[META-PROMPT]
Đánh giá prompt sau đây tôi đang dùng để [mục đích] và giúp tôi cải thiện nó:

"""
[prompt hiện tại của bạn]
"""

Hãy đánh giá prompt này theo các tiêu chí:
1. Clarity (1-10): Prompt có rõ ràng không?
2. Specificity (1-10): Prompt có đủ cụ thể không?
3. Context (1-10): Prompt cung cấp đủ ngữ cảnh không?
4. Structure (1-10): Cấu trúc prompt có tối ưu không?
5. Guidance (1-10): Prompt có hướng dẫn đủ cho kết quả mong muốn không?

Sau đó, hãy:
1. Chỉ ra 3 điểm mạnh của prompt hiện tại
2. Xác định 3 điểm yếu cần cải thiện
3. Đề xuất phiên bản cải tiến của prompt
4. Giải thích các thay đổi và lý do đằng sau chúng
```

### 3. Project-specific Prompt Library

Xây dựng thư viện prompt cho dự án cụ thể:

```
[PROJECT PROMPT LIBRARY]
Hãy giúp tôi xây dựng một thư viện prompt tùy chỉnh cho dự án [tên dự án] với thông tin context sau:

Thông tin dự án:
- Mô tả dự án: [mô tả]
- Tech stack: [list]
- Team composition: [roles]
- Methodology: [Agile/Scrum/Kanban]
- Các tools sử dụng: [Jira, Git, etc.]
- Quy trình đặc thù: [mô tả ngắn gọn]
- Định dạng tài liệu: [conventions]

Hãy tạo một bộ 7-10 prompt templates tùy chỉnh cho các use cases phổ biến trong dự án này, bao gồm:
1. Daily standup summary
2. Sprint planning preparation
3. User story creation specific to our product
4. [other use cases relevant to project]

Mỗi prompt template cần:
- Tiêu đề rõ ràng về use case
- Placeholder cho các biến dự án cụ thể
- Cấu trúc tối ưu với context, instruction, format
- Giải thích ngắn gọn về cách sử dụng
```

## ⚡ Thực hành

### Bài tập 1: Tạo và cải thiện prompt cho tình huống thực tế

1. Chọn một tình huống thực tế trong dự án phần mềm (ví dụ: cần viết user stories cho một tính năng mới)
2. Viết prompt ban đầu
3. Sử dụng meta-prompting để đánh giá và cải thiện
4. So sánh kết quả từ các phiên bản prompt khác nhau

### Bài tập 2: Xây dựng thư viện prompt cá nhân

1. Xác định 5-7 tác vụ QTDDA bạn thực hiện thường xuyên
2. Tạo template prompt cho từng tác vụ
3. Thử nghiệm và tinh chỉnh mỗi prompt ít nhất 3 lần
4. Tổ chức chúng thành một thư viện có cấu trúc

### Bài tập 3: Phân tích dự án thật với prompt

1. Chọn một dự án thật hoặc mẫu
2. Áp dụng các prompt phân tích ở trên vào các khía cạnh khác nhau của dự án
3. Đánh giá chất lượng của phân tích AI so với phân tích thủ công
4. Xác định các areas AI có thể hỗ trợ tốt nhất

## 📚 Tài liệu tham khảo

1. [Agile Project Management with AI tools](https://www.atlassian.com/agile/project-management/ai-tools)
2. [INVEST in Good Stories, and SMART Tasks](https://xp123.com/articles/invest-in-good-stories-and-smart-tasks/)
3. [The Art of Effective Sprint Planning](https://www.scrum.org/resources/blog/art-effective-sprint-planning)
4. [Technical Documentation Best Practices](https://www.writethedocs.org/guide/writing/beginners-guide-to-docs/)
5. [Root Cause Analysis Techniques](https://asq.org/quality-resources/root-cause-analysis)
