# Phân tích dữ liệu export bằng AI

## Giới thiệu

Trong module này, chúng ta sẽ tìm hiểu cách khai thác sức mạnh của AI để phân tích dữ liệu export từ Jira và Git, giúp quản lý dự án phần mềm hiệu quả hơn. Việc phân tích thủ công thường tốn thời gian và có thể bỏ sót các insights quan trọng. Với công nghệ AI hiện đại, chúng ta có thể tự động hóa và nâng cao chất lượng phân tích, từ đó đưa ra quyết định dựa trên dữ liệu chính xác.

## Tổng quan về các loại phân tích dữ liệu dự án phần mềm

### 1. Phân tích hiệu suất (Performance Analysis)

#### Velocity (Tốc độ làm việc)

- **Định nghĩa**: Lượng công việc mà team hoàn thành trong một Sprint.
- **Đo lường**: Story points hoặc số lượng issues hoàn thành.
- **Ứng dụng AI**:
  - Phân tích xu hướng velocity qua các sprint
  - So sánh với dự đoán và đưa ra yếu tố ảnh hưởng
  - Dự báo velocity cho các sprint tiếp theo

#### Lead Time & Cycle Time

- **Lead Time**: Thời gian từ khi tạo issue đến khi hoàn thành.
- **Cycle Time**: Thời gian từ khi bắt đầu làm việc đến khi hoàn thành.
- **Ứng dụng AI**:
  - Phân tích thời gian trung bình theo loại issue
  - Xác định các yếu tố ảnh hưởng đến thời gian xử lý
  - Đề xuất cải tiến quy trình dựa trên phân tích

#### Flow Efficiency

- Tỷ lệ thời gian làm việc thực sự trên tổng thời gian chờ đợi.
- **Ứng dụng AI**: Phân tích và đề xuất cải thiện hiệu quả dòng công việc.

### 2. Phân tích chất lượng (Quality Analysis)

#### Defect Density

- Số lượng bug trên mỗi đơn vị công việc (ví dụ: story point).
- **Ứng dụng AI**:
  - Phân tích tỷ lệ lỗi theo module/component
  - Xác định mối tương quan giữa defect và các yếu tố khác

#### Defect Leakage

- Tỷ lệ lỗi bị bỏ sót trong quá trình testing và được phát hiện ở các giai đoạn sau.
- **Ứng dụng AI**: Dự đoán khả năng defect leakage dựa trên các pattern.

#### Technical Debt

- Đánh giá kỹ thuật nợ trong codebase.
- **Ứng dụng AI**: Phân tích comment và độ phức tạp của code để đánh giá technical debt.

### 3. Phân tích nguồn lực (Resource Analysis)

#### Team Capacity

- Khả năng làm việc tối đa của team trong một thời gian nhất định.
- **Ứng dụng AI**:
  - Phân tích capacity theo thời gian thực
  - Dự báo khả năng hoàn thành công việc dựa trên capacity hiện tại

#### Workload Distribution

- Phân bổ công việc giữa các thành viên.
- **Ứng dụng AI**:
  - Phát hiện sự mất cân đối trong phân bố công việc
  - Đề xuất phân bổ công việc tối ưu

#### Skill Matrix & Resource Allocation

- Đánh giá kỹ năng và sự phù hợp của nhân sự với công việc.
- **Ứng dụng AI**: Phân tích hiệu suất của thành viên dựa trên loại công việc được giao.

## Sử dụng AI để xử lý dữ liệu export từ Jira

### 1. Phân tích CSV/Excel từ Jira export

#### Chuẩn bị dữ liệu

- Cách export dữ liệu Jira sang CSV/Excel (đã học ở Module 8)
- Làm sạch dữ liệu trước khi đưa vào AI:
  - Xóa các cột không cần thiết
  - Xử lý giá trị null hoặc không hợp lệ
  - Chuẩn hóa format ngày tháng, thời gian

#### Phân tích với ChatGPT/Claude

```
Prompt mẫu:
Tôi có một file CSV export từ Jira với các cột sau: Issue Key, Summary, Status, Created Date, Resolution Date, Assignee, Story Points, Sprint. Hãy phân tích dữ liệu này để:
1. Tính cycle time trung bình cho mỗi loại issue
2. Xác định velocity trung bình qua các sprint
3. Phát hiện các issue có thời gian xử lý vượt quá trung bình
4. Tìm ra thành viên nào có workload cao nhất
5. Đưa ra xu hướng về hiệu suất team qua các sprint

[Dán dữ liệu CSV vào đây]
```

#### Phân tích với Gemini + Google Sheets

- Tích hợp Google Sheets với Gemini
- Tạo các công thức phân tích tự động với sự hỗ trợ của AI

### 2. Trích xuất insights từ Sprint Reports

#### Phân tích Sprint Goals vs. Achievements

- So sánh mục tiêu sprint với kết quả đạt được
- Xác định pattern thành công/thất bại

#### Scope Changes Analysis

- Phân tích sự thay đổi scope trong sprint
- Đánh giá tác động của unplanned work

#### Completion Rate & Predictability

- Tỷ lệ hoàn thành công việc theo kế hoạch
- Mức độ chính xác trong ước lượng

### 3. Đánh giá tiến độ dựa trên Burndown/Burnup Charts

#### Burndown Pattern Analysis

- Nhận diện các pattern trong burndown chart:
  - Đường burndown lý tưởng
  - Late delivery pattern
  - Early delivery pattern
  - "Cháy nước rút" pattern

#### Burnup Chart & Scope Change

- Phân tích sự thay đổi scope theo thời gian
- Dự đoán khả năng hoàn thành dựa trên xu hướng hiện tại

#### Velocity Prediction

- Dự đoán velocity cho các sprint tiếp theo dựa trên dữ liệu lịch sử
- Xác định các yếu tố ảnh hưởng đến velocity

## Phân tích dữ liệu Git với AI

### 1. Mô hình commit pattern

#### Thời gian và tần suất commit

- Phân tích thời điểm commit phổ biến
- Đánh giá nhịp độ làm việc của team

#### Commit Message Quality

- Phân tích chất lượng commit message
- Phát hiện các commit không tuân theo quy ước

#### Branch Strategy Analysis

- Đánh giá chiến lược branching
- Phân tích thời gian tồn tại của branch

### 2. Code churn và mối quan hệ với chất lượng phần mềm

#### Định nghĩa Code Churn

- Lượng code bị thay đổi trong một khoảng thời gian
- Tầm quan trọng của code churn đối với chất lượng phần mềm

#### Phát hiện Code Churn cao

- Xác định các file/module có code churn cao
- Mối liên hệ giữa code churn và số lượng bug

#### Đề xuất giảm thiểu rủi ro

- Phân tích khu vực cần tăng cường test
- Đề xuất refactoring dựa trên code churn

### 3. Phân bổ công việc giữa các thành viên

#### Contributor Analysis

- Phân tích sự đóng góp của từng thành viên
- Xác định core contributors và chuyên gia theo domain

#### Knowledge Distribution

- Đánh giá sự phân bổ kiến thức trong team
- Phát hiện các "knowledge silos" (tích tụ kiến thức)

#### Collaboration Patterns

- Phân tích mô hình cộng tác giữa các thành viên
- Đề xuất cải thiện cộng tác

## Prompt engineering cho phân tích dự án

### 1. Cấu trúc prompt hiệu quả cho phân tích dữ liệu

#### Nguyên tắc STAR cho phân tích dữ liệu

- **S**ituation: Mô tả rõ bối cảnh dữ liệu
- **T**ask: Xác định mục tiêu phân tích
- **A**ction: Chỉ định cách thức phân tích
- **R**esult: Định dạng kết quả mong muốn

#### Ví dụ prompt phân tích hiệu quả

```
Tôi là Project Manager của một dự án Agile sử dụng Jira. Tôi đang chuẩn bị báo cáo tháng và có dữ liệu export về tiến độ các sprint trong 3 tháng qua.

Dữ liệu bao gồm: Story Points đã hoàn thành, số lượng issues theo trạng thái, thời gian trung bình để hoàn thành mỗi issue, và số lượng bugs được báo cáo theo sprint.

Hãy giúp tôi:
1. Phân tích xu hướng velocity qua các sprint
2. Xác định các sprint có hiệu suất thấp nhất/cao nhất
3. Tìm mối tương quan giữa số lượng bugs và velocity
4. Đề xuất 3 cải thiện dựa trên dữ liệu

Hãy trình bày phân tích theo định dạng:
- Executive Summary (tóm tắt cho stakeholders)
- Chi tiết phân tích (có biểu đồ nếu có thể)
- Khuyến nghị hành động

Dữ liệu:
[CSV DATA]
```

### 2. Kỹ thuật đặt câu hỏi phù hợp với các loại dữ liệu khác nhau

#### Phân tích hiệu suất Sprint

- Câu hỏi về xu hướng velocity
- Câu hỏi về capacity planning
- Câu hỏi về ước lượng

#### Phân tích chất lượng sản phẩm

- Câu hỏi về tỷ lệ bug
- Câu hỏi về technical debt
- Câu hỏi về test coverage

#### Phân tích team dynamics

- Câu hỏi về phân bổ công việc
- Câu hỏi về cộng tác
- Câu hỏi về workload balance

#### Kỹ thuật follow-up prompts

- Cách đặt câu hỏi tiếp theo dựa trên kết quả ban đầu
- Làm sâu sắc phân tích thông qua phỏng vấn AI

## Thực hành và bài tập

1. Export dữ liệu từ một project Jira mẫu (hoặc sử dụng dataset được cung cấp).
2. Áp dụng prompt mẫu đã học để phân tích dữ liệu với công cụ AI.
3. Tạo báo cáo hiệu suất sprint dựa trên kết quả phân tích.
4. So sánh kết quả phân tích của AI với phân tích thủ công.

## Tài liệu tham khảo

- [The Agile Manager's Guide to Metrics](https://www.atlassian.com/agile/project-management/metrics)
- [Actionable Agile Metrics by Daniel Vacanti](https://actionableagile.com/resources)
- [Flow Framework by Mik Kersten](https://flowframework.org/)
- [Git Analytics Best Practices](https://www.gitprime.com/git-analytics-guide)
