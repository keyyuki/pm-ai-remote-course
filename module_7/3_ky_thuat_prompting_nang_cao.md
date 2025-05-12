# 3. Kỹ thuật prompting nâng cao

## 📋 Tổng quan

Sau khi nắm vững cách xây dựng cấu trúc prompt cơ bản, việc tiếp cận các kỹ thuật prompting nâng cao sẽ giúp bạn tận dụng tối đa tiềm năng của các mô hình AI. Các kỹ thuật này không chỉ giúp cải thiện chất lượng kết quả mà còn mở rộng phạm vi ứng dụng của AI trong quản trị dự án phần mềm. Trong module này, chúng ta sẽ khám phá các kỹ thuật prompting nâng cao như Zero-shot, Few-shot, Chain-of-thought và nhiều phương pháp khác để nâng cao khả năng tương tác với AI.

## 🎯 Mục tiêu

- Hiểu và áp dụng được các kỹ thuật Zero-shot, Few-shot Prompting
- Nắm vững phương pháp Chain-of-thought để cải thiện khả năng suy luận của AI
- Học cách sử dụng Self-consistency để tăng độ tin cậy của kết quả
- Thành thạo Role Prompting để định hướng phản hồi từ AI
- Thực hành áp dụng các kỹ thuật nâng cao trong bối cảnh QTDDA

## 📚 Nội dung chi tiết

### 1. Zero-shot Prompting

#### Khái niệm

Zero-shot Prompting là kỹ thuật yêu cầu AI thực hiện nhiệm vụ mà không cung cấp ví dụ hoặc hướng dẫn cụ thể về cách thực hiện nhiệm vụ đó. AI phải dựa vào kiến thức đã được huấn luyện để hoàn thành yêu cầu.

#### Khi nào sử dụng

- Nhiệm vụ đơn giản, quen thuộc với AI
- Khi muốn kết quả đa dạng, sáng tạo
- Khi không có sẵn ví dụ mẫu
- Để kiểm tra khả năng "hiểu" tự nhiên của AI

#### Ví dụ Zero-shot trong QTDDA

**Prompt đơn giản:**

```
Tạo một backlog item cho tính năng "quên mật khẩu" của ứng dụng mobile.
```

**Prompt Zero-shot nâng cao:**

```
Với vai trò là Product Owner, tạo một backlog item đầy đủ cho tính năng "quên mật khẩu" của ứng dụng mobile banking. Backlog item cần bao gồm mô tả, acceptance criteria, và story points estimate.
```

#### Cải thiện Zero-shot Prompting

- **Thêm vai trò và chuyên môn**: "Với vai trò là một Scrum Master có 10 năm kinh nghiệm..."
- **Đặt tiêu chuẩn chất lượng**: "Phản hồi cần đảm bảo tính đầy đủ, chính xác và thực tế"
- **Chỉ định format đầu ra**: "Trình bày dưới dạng bảng với các cột: Task, Owner, Due Date, Status"
- **Thêm bối cảnh**: "Đây là dự án phần mềm cho một ngân hàng lớn với các yêu cầu bảo mật cao"

### 2. Few-shot Prompting

#### Khái niệm

Few-shot Prompting là kỹ thuật cung cấp một số ít ví dụ về cách thực hiện nhiệm vụ trước khi đưa ra yêu cầu chính. Những ví dụ này giúp "định hướng" AI về cách thức, định dạng và phong cách mà bạn mong muốn.

#### Khi nào sử dụng

- Nhiệm vụ phức tạp hoặc có format đặc thù
- Khi muốn kết quả theo một phong cách nhất định
- Khi muốn nhất quán giữa nhiều đầu ra
- Để tạo nội dung theo template cụ thể

#### Cấu trúc Few-shot prompt

1. **Giới thiệu nhiệm vụ**: Mô tả ngắn gọn về nhiệm vụ cần thực hiện
2. **Cung cấp ví dụ**: 2-3 cặp input/output mẫu
3. **Đánh dấu rõ ràng**: Phân biệt giữa ví dụ và yêu cầu thực sự
4. **Đưa ra yêu cầu**: Nêu input mới và yêu cầu output tương ứng

#### Ví dụ Few-shot trong QTDDA

```
Tôi cần viết các bug reports theo định dạng chuẩn. Dưới đây là một số ví dụ:

Ví dụ 1:
Bug ID: BUG-001
Tiêu đề: Login button unresponsive after multiple attempts
Mức độ: High
Môi trường: Chrome 98.0, Windows 11
Bước tái hiện:
1. Navigate to login page
2. Enter invalid credentials
3. Receive error message
4. Try 5 more times with different invalid credentials
5. The login button becomes unclickable
Kết quả thực tế: Button appears gray and doesn't respond to clicks
Kết quả mong đợi: Button should remain functional regardless of login attempts
Người báo cáo: John Smith
Ngày báo cáo: 2025-01-15

Ví dụ 2:
Bug ID: BUG-002
Tiêu đề: Profile image fails to upload for PNG files larger than 2MB
Mức độ: Medium
Môi trường: Safari 15.3, macOS Monterey
Bước tái hiện:
1. Login to user account
2. Navigate to profile settings
3. Try to upload PNG image larger than 2MB
4. System shows spinner indefinitely
Kết quả thực tế: Upload never completes, no error message
Kết quả mong đợi: System should show error message about file size limit
Người báo cáo: Emma Johnson
Ngày báo cáo: 2025-01-18

Bây giờ, hãy viết một bug report theo cùng format với thông tin sau:
- Vấn đề: Khi người dùng thay đổi timezone trong settings, các events trong calendar không được cập nhật đúng giờ
- Xảy ra trên: Firefox 110.0, Ubuntu 22.04
- Mức nghiêm trọng: Cao
- Phát hiện bởi: Nguyễn Văn A vào ngày 12/5/2025
```

#### Cải thiện Few-shot Prompting

- **Chọn ví dụ đa dạng**: Bao quát nhiều trường hợp khác nhau
- **Sắp xếp từ đơn giản đến phức tạp**: Giúp AI "học" dần dần
- **Đánh dấu rõ ràng**: Sử dụng các tag như <EXAMPLE>, <END_EXAMPLE> để phân định
- **Giải thích lý do**: Thêm ghi chú về lý do tại sao ví dụ được viết như vậy

### 3. Chain-of-thought Prompting

#### Khái niệm

Chain-of-thought (CoT) là kỹ thuật yêu cầu AI trình bày quá trình suy nghĩ từng bước trước khi đi đến kết luận cuối cùng. Phương pháp này đặc biệt hiệu quả với các nhiệm vụ đòi hỏi suy luận phức tạp, giải quyết vấn đề hoặc ra quyết định.

#### Khi nào sử dụng

- Nhiệm vụ phân tích và ra quyết định phức tạp
- Khi cần hiểu rõ quá trình suy luận của AI
- Nhiệm vụ đòi hỏi nhiều bước xử lý logic
- Khi độ chính xác quan trọng hơn tốc độ

#### Cấu trúc Chain-of-thought prompt

1. **Yêu cầu tư duy bước-từng-bước**: "Hãy suy nghĩ từng bước"
2. **Đặt câu hỏi kích thích suy nghĩ**: "Chúng ta sẽ phân tích vấn đề này như thế nào?"
3. **Tập trung vào tiến trình**: "Trình bày quá trình suy luận của bạn"
4. **Chia nhỏ vấn đề**: "Hãy chia vấn đề thành các phần nhỏ hơn và giải quyết từng phần"

#### Ví dụ Chain-of-thought trong QTDDA

```
Với tư cách là Project Manager, tôi cần quyết định liệu có nên thêm một nhân sự mới vào team để đáp ứng deadline sắp tới hay không. Hãy giúp tôi phân tích tình huống này bằng cách suy nghĩ từng bước.

Dữ liệu:
- Deadline dự án: 30/7/2025 (còn 6 tuần)
- Khối lượng công việc ước tính còn lại: 120 story points
- Velocity hiện tại của team (5 người): 15 story points/tuần
- Thời gian onboarding nhân sự mới: 2 tuần
- Productivity trung bình của nhân sự mới sau onboarding: 2 story points/tuần
- Chi phí thuê thêm nhân sự: $3,000/tuần
- Penalty nếu trễ deadline: $5,000/tuần

Hãy phân tích:
1. Liệu team hiện tại có khả năng hoàn thành dự án đúng hạn không?
2. Nếu thêm nhân sự mới, liệu có kịp deadline và có hiệu quả về chi phí không?
3. Có giải pháp thay thế nào tốt hơn không?

Lưu ý: Hãy trình bày từng bước suy luận của bạn, bao gồm cả các tính toán và giả định.
```

#### Few-shot Chain-of-thought

Kết hợp cả ví dụ và suy luận từng bước:

```
Tôi cần phân tích một quyết định kinh doanh. Dưới đây là ví dụ về cách tôi muốn bạn suy nghĩ:

Ví dụ:
Câu hỏi: Có nên đầu tư vào hệ thống CI/CD mới với chi phí $50,000?

Suy luận từng bước:
1. Trước tiên, tôi cần hiểu chi phí hiện tại. Team đang mất trung bình 10 giờ/tuần cho việc integration và deployment thủ công.
2. Với 5 developers, mỗi người có rate $60/giờ, chi phí này là: 10 giờ × $60 × 5 người = $3,000/tuần.
3. Trong 1 năm, chi phí này là: $3,000 × 52 tuần = $156,000.
4. Hệ thống CI/CD mới có thể giảm thời gian này xuống còn 1 giờ/tuần. Chi phí mới: 1 giờ × $60 × 5 người = $300/tuần.
5. Chi phí mới trong 1 năm: $300 × 52 tuần = $15,600.
6. Tiết kiệm hàng năm: $156,000 - $15,600 = $140,400.
7. Thời gian ROI: $50,000 ÷ $140,400 × 12 tháng ≈ 4.3 tháng.
8. Ngoài ra, hệ thống mới còn giảm lỗi deployment và cải thiện time-to-market.
9. Kết luận: Nên đầu tư vào hệ thống CI/CD mới vì ROI rất nhanh (dưới 5 tháng) và có nhiều lợi ích không tính được bằng tiền.

Bây giờ, hãy phân tích câu hỏi của tôi với cùng phương pháp suy luận từng bước:
Câu hỏi: Có nên chuyển dự án từ monolithic sang microservices với chi phí ước tính $200,000 và thời gian 3 tháng downtime?

[Phân tích của bạn đi kèm]
```

### 4. Self-consistency

#### Khái niệm

Self-consistency là kỹ thuật yêu cầu AI tạo ra nhiều chuỗi suy luận độc lập và sau đó chọn kết quả phổ biến nhất hoặc đáng tin cậy nhất. Phương pháp này giúp tăng độ tin cậy của kết quả, đặc biệt với các nhiệm vụ phức tạp.

#### Khi nào sử dụng

- Khi cần độ chính xác cao
- Vấn đề có nhiều cách tiếp cận
- Ra quyết định quan trọng
- Đánh giá rủi ro

#### Cấu trúc Self-consistency prompt

1. **Yêu cầu nhiều phương án**: "Hãy đề xuất 3 cách giải quyết khác nhau"
2. **Đánh giá từng phương án**: "Phân tích ưu nhược điểm của mỗi phương án"
3. **So sánh kết quả**: "So sánh kết quả và chọn phương án tối ưu nhất"
4. **Tổng hợp thành kết luận**: "Tổng hợp các insight từ tất cả phương án thành một giải pháp cuối cùng"

#### Ví dụ Self-consistency trong QTDDA

```
Tôi cần đánh giá rủi ro của việc chuyển đổi từ on-premise server sang cloud infrastructure cho dự án hiện tại. Hãy sử dụng phương pháp đánh giá đa chiều:

1. Đầu tiên, hãy phát triển 3 kịch bản đánh giá độc lập, mỗi kịch bản sử dụng một framework khác nhau:
   - Kịch bản 1: Sử dụng SWOT Analysis
   - Kịch bản 2: Sử dụng Cost-Benefit Analysis kèm các metrics
   - Kịch bản 3: Sử dụng Risk Matrix (Likelihood vs Impact)

2. Với mỗi kịch bản, phân tích các khía cạnh:
   - Technical risks
   - Security concerns
   - Cost implications
   - Operational impact
   - Scaling capabilities

3. Sau khi hoàn thành 3 kịch bản, hãy so sánh kết quả:
   - Những rủi ro nào xuất hiện trong cả 3 kịch bản?
   - Có điểm khác biệt nào đáng chú ý không?
   - Mức độ nghiêm trọng của từng rủi ro có nhất quán không?

4. Cuối cùng, đưa ra đánh giá tổng hợp và khuyến nghị dựa trên cả 3 kịch bản.
```

### 5. Role Prompting

#### Khái niệm

Role Prompting là kỹ thuật yêu cầu AI đóng vai một nhân vật, chuyên gia hoặc có một góc nhìn cụ thể khi trả lời câu hỏi. Điều này giúp định hướng phản hồi theo chuyên môn hoặc phong cách mong muốn.

#### Khi nào sử dụng

- Khi cần góc nhìn chuyên gia trong một lĩnh vực
- Khi muốn phản hồi theo phong cách cụ thể
- Để có nhiều góc nhìn đa dạng về cùng một vấn đề
- Trong các tình huống roleplay hoặc mô phỏng

#### Các vai trò hữu ích trong QTDDA

- Project Manager/Scrum Master
- Product Owner
- Software Architect
- QA Engineer
- Security Expert
- UX Specialist
- Stakeholder/Client
- Senior Developer
- DevOps Engineer

#### Ví dụ Role Prompting trong QTDDA

```
Tôi đang xem xét việc chuyển dự án hiện tại từ Waterfall sang Agile/Scrum. Hãy đóng vai các chuyên gia sau và cho tôi lời khuyên từ góc nhìn của họ:

1. Với tư cách là một Agile Coach có 10 năm kinh nghiệm chuyển đổi quy trình, hãy đưa ra lời khuyên về:
   - 3 bước đầu tiên nên thực hiện
   - Các thách thức phổ biến nhất và cách vượt qua
   - Timeline thực tế cho quá trình chuyển đổi

2. Với tư cách là một Project Manager truyền thống, hãy đưa ra:
   - Những lo ngại chính về việc chuyển sang Agile
   - Các khía cạnh của Waterfall nên được giữ lại
   - Cách đảm bảo tính minh bạch và báo cáo trong quá trình chuyển đổi

3. Với tư cách là một Development Team Lead, hãy chia sẻ:
   - Cách chuẩn bị team kỹ thuật cho sự thay đổi
   - Những thay đổi về workflow và tooling
   - Cách duy trì chất lượng code trong quá trình chuyển đổi

Cuối cùng, hãy tổng hợp những insight chính từ cả ba góc nhìn thành một kế hoạch hành động tổng thể.
```

#### Expert Role Prompting

Định nghĩa chuyên sâu về vai trò để có kết quả chất lượng hơn:

```
Hãy đóng vai một Software Architect chuyên về microservices với 15 năm kinh nghiệm trong các dự án enterprise-scale. Bạn đã tham gia xây dựng kiến trúc cho nhiều hệ thống có hàng triệu người dùng và am hiểu sâu về design patterns, distributed systems, và cloud infrastructure.

Với chuyên môn này, hãy review kiến trúc hệ thống của chúng tôi dưới đây và đưa ra các đề xuất cải thiện:

[Mô tả kiến trúc hệ thống]

Trong phản hồi, hãy tập trung vào:
1. Scalability concerns
2. Potential bottlenecks
3. Security considerations
4. Maintainability improvements
5. Cost optimization opportunities

Vui lòng đưa ra phản hồi chuyên nghiệp, thực tế và có tính ứng dụng cao, dựa trên kinh nghiệm thực tế của một Software Architect senior.
```

### 6. Kết hợp các kỹ thuật

#### Few-shot Chain-of-thought với Role Prompting

```
Với vai trò là một Risk Manager có 12 năm kinh nghiệm trong ngành phát triển phần mềm, hãy phân tích rủi ro cho kế hoạch dự án dưới đây. Sử dụng phương pháp suy nghĩ từng bước như ví dụ:

Ví dụ phân tích rủi ro:
Kế hoạch: Chuyển đổi database từ MySQL sang MongoDB trong hệ thống đang hoạt động
Phân tích từng bước:
1. Xác định loại rủi ro: Đây là rủi ro kỹ thuật và rủi ro business liên quan đến downtime.
2. Đánh giá khả năng xảy ra: Cao (80%), vì đây là thay đổi cơ sở hạ tầng quan trọng.
3. Đánh giá tác động: Nghiêm trọng, có thể gây mất dữ liệu hoặc downtime kéo dài.
4. Risk score: 80% × 9/10 = 7.2/10 (Cao)
5. Các biện pháp giảm thiểu:
   - Tạo kế hoạch rollback chi tiết
   - Thực hiện migration theo từng phase nhỏ
   - Chạy song song hai hệ thống trong 1 tháng
   - Lên kế hoạch maintenance window ở thời điểm ít traffic
6. Đánh giá lại sau khi áp dụng biện pháp: Risk score giảm xuống 4.8/10 (Trung bình).

Bây giờ, hãy phân tích kế hoạch dự án sau với phương pháp tương tự:
[Mô tả kế hoạch dự án cần phân tích]
```

#### Role-based Self-consistency

```
Tôi cần đánh giá đa chiều về quyết định chuyển từ monolithic sang microservices architecture. Hãy tư vấn cho tôi với các vai trò chuyên gia sau:

1. Với vai trò Software Architect:
   - Đánh giá kỹ thuật về pros/cons
   - Technical debt hiện tại vs. tương lai
   - Kiến trúc đề xuất cụ thể

2. Với vai trò Product Manager:
   - Tác động đến roadmap sản phẩm
   - Time-to-market considerations
   - User experience impact

3. Với vai trò Finance Director:
   - Cost analysis (short-term vs long-term)
   - ROI calculation
   - Budget considerations

4. Với vai trò DevOps Lead:
   - CI/CD pipeline changes
   - Monitoring challenges
   - Operational considerations

Sau khi cung cấp góc nhìn từ cả 4 vai trò, hãy phân tích những điểm đồng thuận và khác biệt giữa các góc nhìn. Cuối cùng, đưa ra khuyến nghị tổng hợp dựa trên tất cả các góc nhìn này.
```

## 💡 Kỹ thuật nâng cao hơn nữa

### 1. Collaborative Intelligence (CI) Prompting

Thiết lập một "đội" chuyên gia với các chuyên môn bổ sung cho nhau:

```
Tôi muốn tạo một "Digital Project Management Review Board" với 4 chuyên gia ảo để đánh giá kế hoạch dự án của tôi. Các chuyên gia gồm:

1. Diana - Technical Architect: Chuyên về đánh giá kiến trúc, technical debt, và scalability
2. Michael - Agile Coach: Chuyên về quy trình, team dynamics, và delivery methodology
3. Sarah - Risk Manager: Chuyên về risk assessment, contingency planning, và compliance
4. Robert - Business Analyst: Chuyên về business value, stakeholder alignment, và ROI

Kế hoạch dự án của tôi là:
[Chi tiết kế hoạch dự án]

Quy trình review như sau:
1. Mỗi chuyên gia sẽ đánh giá kế hoạch theo chuyên môn của mình (ngắn gọn, 3-5 điểm chính)
2. Sau đó, mỗi chuyên gia được phép đặt 1 câu hỏi hoặc thách thức ý kiến của chuyên gia khác
3. Cuối cùng, cả team đưa ra khuyến nghị chung (3-5 điểm hành động cụ thể)
```

### 2. Scenario Planning Prompting

Yêu cầu AI phân tích nhiều kịch bản khác nhau:

```
Với vai trò là Project Strategy Consultant, hãy phân tích 3 kịch bản khác nhau cho dự án chuyển đổi số của chúng tôi:

1. Kịch bản Aggressive (6 tháng):
   - Assumptions: Đầu tư nguồn lực tối đa, parallel implementation
   - Phân tích: Timelines, resource requirements, risks, benefits

2. Kịch bản Balanced (12 tháng):
   - Assumptions: Phased approach, moderate resource allocation
   - Phân tích: Timelines, resource requirements, risks, benefits

3. Kịch bản Conservative (18 tháng):
   - Assumptions: Minimal disruption, sequential implementation
   - Phân tích: Timelines, resource requirements, risks, benefits

Cho mỗi kịch bản, hãy sử dụng format:
- Timeline & Milestones
- Resource Requirements (people, technology, budget)
- Key Risks & Mitigations
- Business Impact
- Recommendation Score (1-10)

Cuối cùng, đưa ra so sánh side-by-side giữa 3 kịch bản và đề xuất kịch bản tối ưu nhất cho một công ty mid-size (500 nhân viên) với risk tolerance trung bình.
```

### 3. Socratic Prompting

Sử dụng phương pháp đặt câu hỏi Socratic để khám phá vấn đề sâu hơn:

```
Tôi muốn sử dụng phương pháp Socratic để đánh giá kỹ lưỡng quyết định technology stack cho dự án mới. Hãy đóng vai một Socratic Coach và hướng dẫn tôi thông qua quá trình đặt câu hỏi để đi đến quyết định tốt nhất.

Technology stack đang cân nhắc: MERN (MongoDB, Express, React, Node.js) vs LAMP (Linux, Apache, MySQL, PHP)

Hãy đưa ra các câu hỏi Socratic theo trình tự sau:
1. Câu hỏi làm rõ về requirements và constraints (2-3 câu hỏi)
2. Câu hỏi thách thức các assumptions (2-3 câu hỏi)
3. Câu hỏi về evidence và reasoning (2-3 câu hỏi)
4. Câu hỏi về viewpoints và perspectives (2-3 câu hỏi)
5. Câu hỏi về implications và consequences (2-3 câu hỏi)

Cuối cùng, tổng hợp key insights từ quá trình đặt câu hỏi và gợi ý framework để đưa ra quyết định cuối cùng.
```

## ⚡ Thực hành

### Bài tập 1: Zero-shot vs Few-shot

So sánh kết quả của zero-shot và few-shot prompting cho cùng một nhiệm vụ:

1. Viết một prompt zero-shot để tạo user story cho tính năng "two-factor authentication"
2. Viết một prompt few-shot (với 2 ví dụ) cho cùng nhiệm vụ
3. So sánh kết quả và rút ra bài học

### Bài tập 2: Chain-of-thought cho Risk Assessment

Tạo một prompt chain-of-thought để phân tích rủi ro cho một tính năng mới trong ứng dụng của bạn.

### Bài tập 3: Role Prompting đa chiều

Tạo prompt yêu cầu AI đóng vai 3 stakeholder khác nhau (Product Owner, Developer, End User) để đánh giá một tính năng từ nhiều góc nhìn.

## 📚 Tài liệu tham khảo

1. [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903)
2. [Few-Shot Prompting for Language Model Skills](https://arxiv.org/abs/2202.12837)
3. [Self-Consistency Improves Chain of Thought Reasoning in Language Models](https://arxiv.org/abs/2203.11171)
4. [Role-Play with Large Language Models](https://arxiv.org/abs/2305.16367)
5. [Socratic Questioning for Prompt Engineering](https://arxiv.org/abs/2305.09571)
