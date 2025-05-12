# 1. Giới thiệu về Prompt Engineering

## 📋 Tổng quan

Prompt Engineering là nghệ thuật và khoa học của việc thiết kế, tối ưu hóa và cải thiện các "câu lệnh" (prompts) được đưa cho mô hình AI nhằm thu được kết quả mong muốn. Trong bối cảnh các mô hình ngôn ngữ lớn (LLM) như ChatGPT, Gemini, Claude ngày càng phát triển, Prompt Engineering đã trở thành một kỹ năng thiết yếu giúp người dùng khai thác tối đa tiềm năng của AI, đặc biệt trong lĩnh vực quản trị dự án phát triển phần mềm.

## 🎯 Mục tiêu

- Hiểu được khái niệm và tầm quan trọng của Prompt Engineering
- Nắm được cách thức hoạt động cơ bản của các mô hình AI trong việc xử lý prompt
- Nhận biết các yếu tố ảnh hưởng đến chất lượng phản hồi của AI
- Hiểu được ứng dụng cụ thể của Prompt Engineering trong QTDDA

## 📚 Nội dung chi tiết

### 1. Khái niệm Prompt Engineering và tầm quan trọng

#### Định nghĩa

Prompt Engineering là quá trình thiết kế, tối ưu hóa và tinh chỉnh các câu lệnh đầu vào (prompts) để hướng dẫn mô hình AI sinh ra kết quả có chất lượng, chính xác và phù hợp với nhu cầu của người dùng.

#### Tầm quan trọng

- **Cầu nối giữa ý định và kết quả**: Prompt đóng vai trò trung gian giữa ý định của người dùng và khả năng của AI. Một prompt tốt giúp AI hiểu chính xác những gì bạn cần.
- **Tiết kiệm thời gian và công sức**: Thay vì phải thử nhiều lần, một prompt được thiết kế tốt có thể cho kết quả mong muốn ngay từ đầu.
- **Tận dụng tối đa khả năng của AI**: Các mô hình AI hiện đại có nhiều khả năng ẩn mà không phải lúc nào cũng được kích hoạt thông qua prompt đơn giản.
- **Đảm bảo tính nhất quán**: Prompt tốt giúp nhận được kết quả nhất quán khi sử dụng lại và chia sẻ với người khác.

#### Vai trò trong quản lý dự án phần mềm

- Hỗ trợ ra quyết định phức tạp
- Tự động hóa các tác vụ lặp lại
- Tạo ra nội dung chất lượng cao (tài liệu, báo cáo, mã)
- Phân tích dữ liệu dự án nhanh chóng

### 2. Cách các mô hình AI "hiểu" và xử lý prompt

#### Cơ chế hoạt động cơ bản của LLM

- **Mô hình xác suất**: AI dự đoán từng token (đơn vị từ/ký tự) tiếp theo dựa trên ngữ cảnh đã có
- **Chuỗi suy luận**: AI xây dựng chuỗi suy luận dựa trên dữ liệu huấn luyện và prompt
- **Văn bản là giao diện**: Mọi tương tác với AI đều thông qua văn bản (text-in, text-out)

#### Quy trình xử lý prompt

1. **Tokenization**: Chuyển đổi prompt thành các "token" (đơn vị xử lý)
2. **Embedding**: Chuyển các token thành dạng biểu diễn số học mà máy tính hiểu được
3. **Phân tích ngữ cảnh**: Đánh giá mối quan hệ giữa các token và xác định ngữ cảnh
4. **Sinh kết quả**: Tạo ra chuỗi token đầu ra dựa trên xác suất cao nhất
5. **Detokenization**: Chuyển đổi chuỗi token thành văn bản người dùng có thể đọc được

#### Giới hạn của AI trong việc hiểu prompt

- **Thiếu bối cảnh**: AI không biết thông tin ngoài prompt và dữ liệu huấn luyện
- **Không thực sự "hiểu"**: AI không có trí thông minh thật sự mà chỉ mô phỏng hiểu biết
- **Hallucination**: Có thể tạo ra thông tin sai lệch khi không chắc chắn
- **Giới hạn ngữ cảnh**: Mỗi mô hình có giới hạn về độ dài văn bản có thể xử lý (context window)

### 3. Các yếu tố ảnh hưởng đến chất lượng kết quả từ AI

#### Yếu tố liên quan đến prompt

- **Độ rõ ràng và cụ thể**: Prompt càng rõ ràng, kết quả càng chính xác
- **Cấu trúc và tổ chức**: Prompt có cấu trúc logic giúp AI xử lý tốt hơn
- **Ngôn ngữ sử dụng**: Dùng từ ngữ chính xác, tránh mơ hồ và đa nghĩa
- **Độ dài và phức tạp**: Prompt quá dài hoặc quá phức tạp có thể gây nhầm lẫn

#### Yếu tố liên quan đến mô hình AI

- **Phiên bản mô hình**: GPT-4 cho kết quả tốt hơn GPT-3.5 trong nhiều tác vụ
- **Nhiệt độ (Temperature)**: Tham số điều chỉnh độ sáng tạo/ngẫu nhiên
- **Dữ liệu huấn luyện**: Thời điểm dữ liệu huấn luyện kết thúc ảnh hưởng đến kiến thức của mô hình
- **Thông số kỹ thuật khác**: max_tokens, top_p, frequency_penalty, presence_penalty...

#### Yếu tố liên quan đến ngữ cảnh

- **Lịch sử cuộc trò chuyện**: Các prompt/phản hồi trước đó ảnh hưởng đến kết quả
- **Kiến thức chuyên ngành**: Mức độ chuyên môn hóa của lĩnh vực đang đề cập
- **Độ phức tạp của nhiệm vụ**: Task đơn giản thường có kết quả tốt hơn task phức tạp

### 4. Vai trò của Prompt Engineering trong QTDDA

#### Tối ưu hóa quy trình

- **Tự động hóa tác vụ lặp lại**: Tạo template email, báo cáo, cập nhật trạng thái
- **Hỗ trợ đưa ra quyết định**: Phân tích rủi ro, ưu tiên hóa tính năng, phân bổ nguồn lực
- **Cải thiện giao tiếp**: Tóm tắt cuộc họp, tạo nội dung trình bày, làm rõ yêu cầu

#### Ứng dụng cụ thể

1. **Quản lý yêu cầu**:

   - Chuyển đổi yêu cầu khách hàng thành User Stories
   - Phát hiện mâu thuẫn trong đặc tả
   - Tạo tiêu chí chấp nhận

2. **Lập kế hoạch**:

   - Ước lượng công việc
   - Phân tích phụ thuộc giữa các task
   - Dự báo timeline và rủi ro

3. **Phát triển và kiểm thử**:

   - Tạo mã mẫu và pseudocode
   - Thiết kế test cases
   - Code review và gợi ý cải thiện

4. **Giám sát và báo cáo**:
   - Phân tích dữ liệu tiến độ
   - Tạo dashboard trực quan
   - Tự động báo cáo tình trạng dự án

#### Lợi ích của Prompt Engineering tốt trong QTDDA

- **Nâng cao năng suất**: Tự động hóa các tác vụ thường xuyên, giải phóng thời gian cho công việc sáng tạo
- **Cải thiện chất lượng**: Giảm sai sót, nhất quán trong văn phong và định dạng
- **Đẩy nhanh ra quyết định**: Phân tích nhanh chóng các lựa chọn và đề xuất giải pháp
- **Hỗ trợ học tập**: Giúp team thành viên học hỏi kiến thức quản lý dự án và công nghệ mới

## 💡 Thách thức và hạn chế

### Thách thức trong việc áp dụng Prompt Engineering

- **Độ biến thiên kết quả**: Cùng một prompt có thể cho kết quả khác nhau ở các lần chạy khác nhau
- **Kiểm chứng thông tin**: AI có thể tự tin đưa ra thông tin sai lệch
- **Yêu cầu thực hành**: Cần thời gian và thực hành để thành thạo kỹ năng viết prompt
- **Phụ thuộc vào công cụ**: Mỗi công cụ AI có đặc điểm riêng và yêu cầu cách tiếp cận khác nhau

### Hướng dẫn khắc phục

- **Xác minh kết quả quan trọng**: Luôn kiểm tra thông tin từ AI với nguồn đáng tin cậy
- **Iterative approach**: Cải thiện prompt dần dần qua nhiều lần thử
- **Sử dụng hệ thống prompt**: Xây dựng bộ sưu tập prompt hiệu quả cho các tác vụ thường gặp
- **Tạo thói quen review**: Đánh giá và cải tiến prompt thường xuyên

## ⚡ Thực hành

### Bài tập 1: Phân tích prompt

Phân tích các prompt sau và nhận diện điểm mạnh, điểm yếu:

**Prompt 1:**

```
Tạo user story.
```

**Prompt 2:**

```
Với vai trò là một Product Owner có kinh nghiệm, hãy giúp tôi tạo 3 User Stories theo chuẩn INVEST cho tính năng "Thanh toán online" trong ứng dụng thương mại điện tử. Mỗi User Story cần có format "As a [role], I want [capability], so that [benefit]" và ít nhất 3 tiêu chí chấp nhận theo định dạng Given-When-Then. Đối tượng người dùng chính là khách hàng mua sắm online và người bán hàng.
```

### Bài tập 2: Cải thiện prompt

Cải thiện prompt sau để nhận được kết quả tốt hơn:

```
Giúp tôi lập kế hoạch sprint cho dự án phần mềm.
```

### Bài tập 3: Nhận diện yếu tố ảnh hưởng

Liệt kê 5 yếu tố có thể ảnh hưởng đến chất lượng kết quả khi bạn sử dụng AI để phân tích rủi ro dự án phần mềm.

## 📚 Tài liệu tham khảo

1. [OpenAI - Introduction to Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering)
2. [Google Bard Prompt Design](https://ai.google.dev/docs/prompt_best_practices)
3. [Anthropic Claude Prompt Engineering](https://docs.anthropic.com/claude/docs/introduction-to-prompt-design)
4. [The Art of ChatGPT Prompting: A Guide to Crafting Clear and Effective Prompts](https://www.amazon.com/Art-ChatGPT-Prompting-Crafting-Effective-ebook/dp/B0BXG74J9V)
5. [Prompt Engineering Institute Resources](https://www.promptingguide.ai/introduction)
