# 2. Cấu trúc prompt hiệu quả

## 📋 Tổng quan

Việc xây dựng một prompt có cấu trúc hiệu quả là yếu tố then chốt để tận dụng tối đa sức mạnh của các mô hình AI. Một prompt được thiết kế tốt không chỉ giúp AI hiểu chính xác yêu cầu của người dùng mà còn định hướng đầu ra theo format mong muốn. Trong module này, chúng ta sẽ tìm hiểu cách cấu trúc prompt để đạt được kết quả tốt nhất, đặc biệt trong bối cảnh quản trị dự án phát triển phần mềm.

## 🎯 Mục tiêu

- Nắm vững các thành phần cơ bản của một prompt hiệu quả
- Học cách làm rõ yêu cầu và giới hạn phạm vi trong prompt
- Hiểu cách sử dụng ngôn ngữ rõ ràng, chính xác để giao tiếp với AI
- Biết cách tùy chỉnh prompt phù hợp với từng công cụ AI khác nhau
- Thực hành xây dựng prompt có cấu trúc cho các tình huống QTDDA

## 📚 Nội dung chi tiết

### 1. Các thành phần cơ bản của một prompt tốt

#### a. Ngữ cảnh (Context)

Cung cấp thông tin nền tảng để AI hiểu bối cảnh của yêu cầu.

**Ví dụ không có ngữ cảnh:**

```
Viết user story cho tính năng đăng nhập.
```

**Ví dụ có ngữ cảnh:**

```
Tôi đang phát triển một ứng dụng di động cho phép người dùng theo dõi chi tiêu cá nhân. Đối tượng người dùng là những người trẻ (25-35 tuổi) muốn quản lý tài chính cá nhân tốt hơn. Ứng dụng đã có tính năng đăng ký tài khoản bằng email. Viết user story cho tính năng đăng nhập.
```

**Các yếu tố ngữ cảnh quan trọng trong QTDDA:**

- Loại dự án và ngành (ví dụ: ứng dụng web, mobile, hệ thống nội bộ)
- Công nghệ sử dụng (tech stack)
- Đối tượng người dùng
- Giai đoạn phát triển (requirement, design, development, testing)
- Phương pháp phát triển (Agile, Waterfall, DevOps)
- Các ràng buộc đặc thù (thời gian, ngân sách, luật định...)

#### b. Hướng dẫn (Instructions)

Mô tả rõ ràng những gì bạn muốn AI thực hiện.

**Nguyên tắc:**

- Sử dụng động từ hành động rõ ràng
- Chia nhỏ các yêu cầu phức tạp thành từng bước
- Đặt ưu tiên rõ ràng nếu có nhiều yêu cầu
- Chỉ định mức độ chi tiết mong muốn

**Ví dụ hướng dẫn không hiệu quả:**

```
Phân tích dự án.
```

**Ví dụ hướng dẫn hiệu quả:**

```
Phân tích kế hoạch dự án dưới đây và:
1. Xác định 3 rủi ro chính có thể ảnh hưởng đến timeline
2. Đề xuất biện pháp giảm thiểu cho từng rủi ro
3. Đánh giá tính khả thi của kế hoạch dựa trên nguồn lực đã đề cập
```

#### c. Ví dụ/Dữ liệu đầu vào (Examples/Input)

Cung cấp mẫu hoặc dữ liệu cụ thể giúp AI hiểu cách thức hoặc định dạng mong muốn.

**Cách cung cấp ví dụ hiệu quả:**

- Sử dụng ví dụ có liên quan trực tiếp đến bối cảnh
- Cung cấp cả ví dụ tốt và không tốt nếu cần
- Đánh dấu rõ phần nào là ví dụ, phần nào là yêu cầu chính

**Ví dụ:**

```
Tôi muốn bạn viết một email thông báo về việc trì hoãn deadline dự án cho client. Dưới đây là một ví dụ về tone và style tôi muốn:

---EXAMPLE START---
Subject: Project Timeline Update - E-commerce Platform

Dear [Client Name],

I hope this email finds you well. I'm writing to inform you about an update to our project timeline for the E-commerce Platform development.

After thorough assessment of the current progress and considering the additional requirements discussed in our last meeting (May 5th), we need to adjust our delivery schedule. The initial launch date of June 15th will need to be extended to June 30th.

This adjustment will ensure we can properly implement the newly requested payment gateway integration while maintaining the high quality standards we both expect.

Please let me know if you would like to discuss this further. I'm available for a call tomorrow between 10AM-2PM.

Best regards,
[Project Manager Name]
---EXAMPLE END---

Bây giờ, hãy viết một email tương tự cho tình huống: Dự án mobile app của chúng tôi bị trễ 2 tuần do team backend gặp vấn đề kỹ thuật với API authentication. Client là Công ty ABC, người nhận là Ông Nguyễn Văn A, Giám đốc CNTT. Deadline ban đầu là 20/6/2025, nay dời sang 4/7/2025.
```

#### d. Format đầu ra (Output format)

Chỉ định rõ ràng cấu trúc, định dạng và kiểu kết quả mà bạn mong đợi.

**Các yếu tố format đầu ra:**

- Cấu trúc (tiêu đề, đoạn, danh sách, bảng...)
- Độ dài (số từ, số đoạn, thời gian đọc)
- Ngôn ngữ và tone (formal, conversational, technical...)
- Định dạng đặc biệt (JSON, XML, Markdown, HTML...)

**Ví dụ không chỉ định format:**

```
Viết daily report về tiến độ dự án.
```

**Ví dụ có chỉ định format:**

```
Viết daily report về tiến độ dự án sử dụng format markdown với các phần sau:
- Tiêu đề: Daily Progress Report - [Ngày hiện tại]
- Phần 1: Accomplishments (danh sách bullet points, tối đa 5 điểm)
- Phần 2: Blockers (danh sách đánh số, mỗi blocker kèm mức độ nghiêm trọng)
- Phần 3: Plan for Tomorrow (danh sách checkbox)
- Phần 4: Metrics (bảng với 3 chỉ số: Tasks Completed, Hours Spent, Burndown Percentage)

Giữ ngắn gọn, tối đa 300 từ, giọng điệu chuyên nghiệp nhưng không quá formal.
```

### 2. Kỹ thuật làm rõ yêu cầu và giới hạn phạm vi

#### Tăng độ chính xác của prompt

- **Sử dụng thông tin định lượng**: Thay vì "viết một báo cáo dài", hãy nói "viết báo cáo khoảng 500 từ"
- **Chỉ định cụ thể về độ sâu**: "Phân tích sơ bộ" vs "Phân tích chuyên sâu với các ví dụ cụ thể"
- **Xác định rõ đối tượng**: "Viết hướng dẫn sử dụng cho developer junior có dưới 1 năm kinh nghiệm"

#### Giới hạn phạm vi

- **Nêu rõ những gì KHÔNG muốn đề cập**: "Không bao gồm các vấn đề liên quan đến bảo mật"
- **Giới hạn thời gian/không gian**: "Chỉ tập trung vào thay đổi trong sprint hiện tại"
- **Chỉ định mức độ ưu tiên**: "Ưu tiên phân tích các vấn đề performance hơn là UX"

#### Xử lý thông tin không đầy đủ

- **Yêu cầu AI đặt câu hỏi**: "Nếu bạn cần thêm thông tin để trả lời đầy đủ, hãy liệt kê các câu hỏi cần làm rõ"
- **Chỉ định cách xử lý khi thiếu thông tin**: "Nếu thiếu thông tin, hãy đưa ra các giả định hợp lý và nêu rõ đó là giả định"
- **Cho phép trả lời từng phần**: "Trả lời những phần bạn có thể, và chỉ ra phần nào cần thêm thông tin"

#### Ví dụ prompt có giới hạn phạm vi rõ ràng:

```
Tôi cần tạo một test plan cho tính năng đăng nhập của ứng dụng web. Hãy giúp tôi với các điều kiện sau:

- PHẠM VI: Chỉ tập trung vào functional testing (không bao gồm performance hay security testing)
- ĐỐI TƯỢNG: Test plan này sẽ được sử dụng bởi QA engineer junior
- ĐỘ CHI TIẾT: Mỗi test case cần có steps, expected results, và preconditions
- GIỚI HẠN: Không quá 10 test cases, ưu tiên test cases critical
- ĐỊNH DẠNG: Sử dụng bảng markdown với các cột (ID, Description, Steps, Expected Result, Priority)

Nếu bạn cần thêm thông tin về tech stack hoặc requirements cụ thể, hãy liệt kê các câu hỏi.
```

### 3. Sử dụng ngôn ngữ rõ ràng, chính xác

#### Lựa chọn từ vựng

- **Sử dụng thuật ngữ đúng nghĩa**: Áp dụng thuật ngữ chuyên ngành QTDDA và phát triển phần mềm
- **Tránh từ ngữ mơ hồ**: "tốt", "hiệu quả", "sớm" → "đạt 98% test pass rate", "giảm 30% thời gian load", "trước 15/7/2025"
- **Cân nhắc đồng nghĩa và khác biệt**: "Review", "inspect", "examine", "analyze" có những sắc thái khác nhau

#### Cấu trúc câu

- **Câu ngắn, rõ ràng**: Chia câu dài thành các câu ngắn hơn
- **Thứ tự logic**: Subject-Verb-Object, điều kiện trước rồi mới đến kết quả
- **Liên kết rõ ràng**: Sử dụng từ nối phù hợp để liên kết các ý

#### Xử lý đa nghĩa

- **Định nghĩa thuật ngữ**: "Trong ngữ cảnh này, 'deployment' có nghĩa là..."
- **Cung cấp ngữ cảnh**: "Khi tôi nói 'user', tôi đang đề cập đến khách hàng cuối, không phải admin"
- **Làm rõ từ đa nghĩa**: "Sprint (trong Agile, không phải chạy nước rút)"

#### Ví dụ về cải thiện ngôn ngữ:

**Prompt không rõ ràng:**

```
Tìm lỗi trong code và làm nó tốt hơn.
```

**Prompt rõ ràng, chính xác:**

```
Xem xét đoạn code JavaScript dưới đây và:
1. Xác định các lỗi về cú pháp hoặc logic (nếu có)
2. Chỉ ra các vấn đề về hiệu suất, đặc biệt là trong vòng lặp
3. Đề xuất cải tiến để làm code dễ bảo trì hơn, tuân thủ các best practices của ES6
4. Viết lại đoạn code với các cải tiến đề xuất, kèm theo comments giải thích thay đổi

[code đi kèm]
```

### 4. Cách tạo prompt tối ưu cho từng công cụ AI khác nhau

#### Prompt cho ChatGPT (OpenAI)

- **Tận dụng system message**: Thiết lập vai trò, tone, phong cách từ đầu
- **Nhận thức về cắt ngữ cảnh**: Giữ thông tin quan trọng nhất ở đầu prompt
- **Sử dụng JSON mode** khi cần output có cấu trúc chặt chẽ
- **Control parameters**: Temperature (0-2), Top P, Frequency/Presence penalty

**Ví dụ system message hiệu quả:**

```
Bạn là một chuyên gia quản lý dự án phần mềm với 15 năm kinh nghiệm trong phương pháp Agile/Scrum. Nhiệm vụ của bạn là cung cấp hướng dẫn chính xác, súc tích và thực tế. Luôn đưa ra ví dụ cụ thể cho mỗi khái niệm. Khi đưa ra lời khuyên, hãy dựa trên best practices trong ngành và chỉ ra những trade-offs. Nếu một câu hỏi không rõ ràng, hãy đặt câu hỏi làm rõ thay vì đưa ra giả định.
```

#### Prompt cho Gemini (Google)

- **Multimodal prompting**: Kết hợp văn bản với hình ảnh/biểu đồ
- **Tận dụng khả năng tìm kiếm thời gian thực**
- **Cấu trúc rõ ràng**: Gemini thích câu ngắn, mệnh đề rõ ràng

#### Prompt cho Claude (Anthropic)

- **Tận dụng context window lớn**: Claude có thể xử lý tài liệu dài
- **Sử dụng dấu <xml>**: Claude phản ứng tốt với thẻ XML để phân chia nội dung
- **Khả năng reasoning**: Yêu cầu Claude lý luận từng bước

**Ví dụ prompt với XML tags:**

```
<instruction>
Phân tích kế hoạch dự án dưới đây và đánh giá các rủi ro tiềm ẩn.
</instruction>

<project_plan>
[Nội dung kế hoạch dự án]
</project_plan>

<output_format>
Cung cấp phân tích theo cấu trúc sau:
1. Tóm tắt dự án (2-3 câu)
2. Timeline assessment
3. Resource allocation assessment
4. Top 5 risks with severity rating
5. Mitigation suggestions for each risk
</output_format>
```

#### Prompt cho GitHub Copilot

- **Tập trung vào mã**: Mô tả chức năng, input/output, edge cases
- **Chỉ định ngôn ngữ và framework**: "in Python using Flask"
- **Yêu cầu comments**: Đề nghị code có comments giải thích

**Ví dụ:**

```
// Implement a function that validates a user's password with the following requirements:
// - At least 8 characters long
// - Contains at least one uppercase letter
// - Contains at least one lowercase letter
// - Contains at least one number
// - Contains at least one special character (!@#$%^&*()_+)
// Function should return true if valid, false otherwise
// Include error handling and write unit tests for edge cases

function validatePassword(password) {
  // Your implementation here
}
```

### 5. Chiến lược lặp và cải thiện prompt

#### Iterative prompting

1. **Start simple**: Bắt đầu với prompt đơn giản
2. **Analyze response**: Đánh giá kết quả, xác định điểm cần cải thiện
3. **Refine**: Điều chỉnh prompt dựa trên phản hồi
4. **Repeat**: Lặp lại cho đến khi đạt kết quả mong muốn

#### Điều chỉnh dần dần

- **Thêm chi tiết**: Bổ sung thông tin ngữ cảnh, ví dụ, định dạng
- **Làm rõ hướng dẫn**: Điều chỉnh yêu cầu dựa trên những gì AI hiểu sai
- **Thay đổi cách diễn đạt**: Thử các cách khác để truyền đạt ý tưởng tương tự

#### Sử dụng phản hồi của AI

- **Ask for feedback**: "Làm thế nào tôi có thể cải thiện prompt này?"
- **Self-critique**: "Đánh giá prompt của tôi và đề xuất cách làm tốt hơn"
- **Ask for alternatives**: "Viết lại prompt này theo 3 cách khác"

## 💡 Kỹ thuật nâng cao

### 1. Template hóa prompt

Tạo các template cho các tác vụ lặp lại thường xuyên trong QTDDA:

**Template cho User Story:**

```
Tôi cần tạo [số lượng] User Stories cho tính năng [tên tính năng] trong [loại ứng dụng].

Bối cảnh:
- Đối tượng người dùng: [mô tả người dùng]
- Mục đích chính của tính năng: [mô tả mục đích]
- Các ràng buộc kỹ thuật: [nếu có]

Mỗi User Story cần tuân thủ định dạng:
"As a [role], I want [capability], so that [benefit]"

Mỗi User Story cần có ít nhất [số lượng] tiêu chí chấp nhận theo format:
"Given [context], When [action], Then [expected result]"

Đánh giá từng User Story theo tiêu chí INVEST.
```

**Template cho báo cáo tiến độ:**

```
Tạo báo cáo tiến độ dự án [tên dự án] cho tuần kết thúc ngày [ngày].

Dữ liệu:
- Hoàn thành: [x] trong tổng số [y] tasks
- Blockers hiện tại: [liệt kê]
- Rủi ro mới phát sinh: [liệt kê]
- Milestone sắp tới: [mô tả] vào [ngày]

Định dạng báo cáo:
1. Executive Summary (1 đoạn)
2. Progress Details (bảng)
3. Risk Assessment (bullet points)
4. Next Steps (đánh số)
5. Support Needed (nếu có)

Độ dài: 1 trang A4
Tone: Professional, factual
Đối tượng: Project stakeholders
```

### 2. Modular Prompting

Chia prompt phức tạp thành các module nhỏ hơn, dễ quản lý:

```
[CONTEXT]
Tôi đang quản lý dự án phát triển ứng dụng mobile cho hệ thống đặt lịch y tế.

[TASK]
Tạo một test strategy document.

[SCOPE]
Tập trung vào các loại testing cần thực hiện, không đi vào chi tiết test cases.

[CONSTRAINTS]
- Team size: 2 QA engineers
- Timeline: 3 tuần cho testing
- Phải hỗ trợ iOS và Android

[OUTPUT FORMAT]
Document cấu trúc với các section:
1. Introduction
2. Test Approach
3. Test Types
4. Test Environment
5. Test Schedule
6. Risk Assessment
7. Exit Criteria

[STYLE]
Ngắn gọn, chuyên nghiệp, dành cho technical audience
```

### 3. Điều khiển trình tự suy luận của AI

Hướng dẫn AI suy nghĩ từng bước:

```
Phân tích yêu cầu dưới đây và xây dựng acceptance criteria. Trước khi đưa ra kết quả cuối cùng, hãy thực hiện các bước sau:

Bước 1: Xác định đối tượng người dùng chính và mục tiêu của họ
Bước 2: Liệt kê các luồng xử lý chính và luồng thay thế
Bước 3: Xác định các edge cases và error scenarios
Bước 4: Từ những thông tin trên, viết acceptance criteria theo format Given-When-Then

Yêu cầu: [mô tả yêu cầu]
```

## ⚡ Thực hành

### Bài tập 1: Phân tích và cải thiện prompt

Phân tích prompt sau và viết phiên bản cải tiến:

```
Tạo roadmap cho dự án phần mềm quản lý nhân sự.
```

### Bài tập 2: Xây dựng template prompt cho QTDDA

Xây dựng template prompt cho một trong các tác vụ sau:

- Sprint Planning
- Risk Assessment
- Technical Documentation Review
- Retrospective Meeting Preparation

### Bài tập 3: Tạo prompt có cấu trúc đầy đủ

Tạo một prompt đầy đủ (bao gồm context, instructions, examples và output format) cho việc phân tích và ước lượng user stories trong một sprint planning.

## 📚 Tài liệu tham khảo

1. [OpenAI - Advanced Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering/advanced-techniques)
2. [Anthropic - Structured Prompting Guide](https://docs.anthropic.com/claude/docs/structured-prompting-guide)
3. [Learn Prompting - Crafting Effective Prompts](https://learnprompting.org/docs/category/crafting-effective-prompts)
4. [Prompt Engineering for Developers - DeepLearning.AI Course](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)
5. [The Art of Clarity: Writing Clear Instructions for LLMs](https://writings.stephenwolfram.com/2023/01/wolframalpha-as-the-way-to-bring-computational-knowledge-superpowers-to-chatgpt/)
