# Thực hành phân tích dữ liệu mẫu

## Giới thiệu

Trong phần cuối của module này, chúng ta sẽ áp dụng kiến thức đã học để thực hành phân tích dữ liệu thực tế. Việc thực hành là bước quan trọng để củng cố kỹ năng và hiểu sâu hơn về cách AI có thể hỗ trợ quản lý dự án phần mềm. Thông qua các workshop và bài tập thực tế, học viên sẽ được trải nghiệm toàn bộ quy trình từ việc chuẩn bị dữ liệu, phân tích với AI, đến tạo báo cáo và đề xuất cải tiến dựa trên insights thu được.

## Workshop thực hành phân tích dữ liệu

### 1. Dataset mẫu từ dự án thực tế (đã ẩn danh)

#### Cấu trúc dataset mẫu

Chúng ta sẽ làm việc với một dataset mẫu đã được ẩn danh từ một dự án phát triển phần mềm thực tế. Dataset bao gồm:

1. **Jira Export Data**:

   - Issues với các trường: Key, Type, Status, Priority, Assignee, Reporter, Created Date, Updated Date, Resolution Date, Sprint, Story Points
   - Sprint Reports cho 6 sprints liên tiếp
   - Burndown/Burnup Charts
   - JQL Export của các Issue Types và Workflows

2. **Git Data**:

   - Commit history
   - Merge/Pull requests
   - Code churn metrics
   - Branch statistics

3. **Additional Context**:
   - Team structure và capacity
   - Project goals và milestones
   - Previous retrospective notes

#### Tải và chuẩn bị dataset

Dataset sẽ được cung cấp dưới dạng các file CSV và JSON. Học viên cần:

1. Tải dataset từ link được cung cấp
2. Kiểm tra tính đầy đủ và nhất quán của dữ liệu
3. Thực hiện các bước tiền xử lý cơ bản như:
   - Chuyển đổi định dạng ngày/giờ phù hợp
   - Xử lý các giá trị null hoặc không hợp lệ
   - Tạo calculated fields nếu cần thiết

### 2. Bài tập tình huống với các vấn đề cần phát hiện

#### Scenario 1: Sprint Performance Analysis

**Bối cảnh**: Bạn là một Project Manager mới được giao phụ trách một dự án đang gặp vấn đề về delivery. Dự án đã trải qua 6 sprints, nhưng các stakeholders không hài lòng về tốc độ và chất lượng.

**Yêu cầu**:

1. Phân tích dữ liệu sprint history
2. Xác định các pattern và vấn đề chính
3. Đề xuất 3-5 cải tiến cụ thể để cải thiện performance

**Dữ liệu cung cấp**:

- Sprint reports
- Velocity charts
- Issue completion statistics
- Team capacity data

**Prompt gợi ý**:

```
Tôi là Project Manager mới của một dự án đang gặp vấn đề về delivery. Dự án đã trải qua 6 sprints và stakeholders không hài lòng về tốc độ và chất lượng. Hãy phân tích dữ liệu sprint history sau đây để giúp tôi:

1. Xác định các pattern và xu hướng về velocity, completion rate, và quality
2. Phát hiện các vấn đề tiềm ẩn ảnh hưởng đến hiệu suất team
3. Đề xuất 3-5 cải tiến cụ thể, khả thi để cải thiện performance

[Dán dữ liệu sprint history]

Hãy cung cấp phân tích chi tiết và đề xuất hành động dựa trên dữ liệu.
```

#### Scenario 2: Quality & Technical Debt Analysis

**Bối cảnh**: Team đang phải đối mặt với số lượng bugs ngày càng tăng và nghi ngờ về technical debt tích tụ. Ban lãnh đạo muốn hiểu rõ tình hình và có kế hoạch hành động cụ thể.

**Yêu cầu**:

1. Phân tích dữ liệu về bugs và code quality
2. Xác định các component/areas có vấn đề nhất
3. Tạo báo cáo technical debt và đề xuất kế hoạch giảm thiểu

**Dữ liệu cung cấp**:

- Bug reports và statistics
- Code churn data từ Git
- Test coverage reports
- Complexity metrics

**Prompt gợi ý**:

```
Team phát triển của chúng tôi đang phải đối mặt với số lượng bugs ngày càng tăng và technical debt tích tụ. Dựa trên dữ liệu sau đây, hãy giúp tôi:

1. Phân tích các mẫu và xu hướng bugs: tần suất, severity, areas ảnh hưởng
2. Xác định các components/modules có vấn đề lớn nhất về chất lượng
3. Đánh giá mức độ technical debt dựa trên code churn, complexity và test coverage
4. Tạo một báo cáo technical health và đề xuất roadmap để cải thiện chất lượng

[Dán dữ liệu về bugs, code quality và technical metrics]

Hãy tạo một báo cáo có cấu trúc rõ ràng với visualizations (mô tả) và actionable recommendations.
```

#### Scenario 3: Resource Allocation & Bottleneck Detection

**Bối cảnh**: Dự án đang gặp vấn đề về timeline và có dấu hiệu của bottlenecks trong quy trình làm việc. CEO muốn hiểu rõ liệu vấn đề là do thiếu nhân lực, phân bổ không hợp lý, hay do quy trình.

**Yêu cầu**:

1. Phân tích workload và capacity của team
2. Xác định bottlenecks trong quy trình
3. Đề xuất phương án tối ưu hóa resource allocation và workflow

**Dữ liệu cung cấp**:

- Team capacity và assignments
- Workflow state transitions
- Issue aging reports
- Dependency maps

**Prompt gợi ý**:

```
Dự án của chúng tôi liên tục bị trễ deadline và chúng tôi cần hiểu rõ nguyên nhân. Dựa trên dữ liệu sau đây về team capacity, workflow và dependencies, hãy giúp tôi:

1. Phân tích workload distribution giữa các thành viên team
2. Xác định các bottlenecks trong quy trình làm việc (states nào có thời gian tồn đọng cao nhất)
3. Đánh giá impact của dependencies lên timeline
4. Đề xuất phương án tối ưu resource allocation và workflow

[Dán dữ liệu về team capacity, workflow transitions, và dependencies]

Hãy cung cấp phân tích định lượng khi có thể và đề xuất 3-5 giải pháp cụ thể, khả thi để cải thiện flow và giảm thiểu bottlenecks.
```

## Quy trình phân tích dữ liệu hoàn chỉnh

### 1. Import dữ liệu vào công cụ AI

#### Chuẩn bị dữ liệu cho phân tích AI

Trước khi import dữ liệu vào công cụ AI, cần thực hiện một số bước chuẩn bị:

1. **Cấu trúc dữ liệu phù hợp**:

   - Đảm bảo định dạng nhất quán (CSV, JSON)
   - Chuẩn hóa tên cột/field
   - Tách dữ liệu thành các phần có kích thước phù hợp nếu quá lớn

2. **Dữ liệu nhạy cảm**:

   - Ẩn danh các thông tin cá nhân
   - Xóa hoặc mã hóa thông tin bảo mật
   - Đảm bảo tuân thủ các chính sách dữ liệu

3. **Context cần thiết**:
   - Cung cấp giải thích về ý nghĩa các trường dữ liệu
   - Mô tả quy trình làm việc để AI hiểu rõ context
   - Đặt rõ mục tiêu phân tích

#### Lựa chọn công cụ AI phù hợp

Mỗi công cụ AI có thế mạnh riêng, việc lựa chọn phụ thuộc vào loại phân tích:

1. **ChatGPT (OpenAI)**:

   - Thế mạnh: Phân tích văn bản, phát hiện pattern, tạo báo cáo
   - Phù hợp cho: Phân tích comments, description, issue summaries

2. **Gemini (Google)**:

   - Thế mạnh: Phân tích dữ liệu dạng bảng, tích hợp với Google Sheets
   - Phù hợp cho: Phân tích số liệu, metrics, trends

3. **Claude (Anthropic)**:
   - Thế mạnh: Xử lý văn bản dài, reasoning
   - Phù hợp cho: Phân tích tài liệu dự án, retrospectives

### 2. Làm sạch và chuẩn bị dữ liệu

#### Data Cleaning với AI

Sử dụng AI để hỗ trợ làm sạch dữ liệu:

1. **Phát hiện và xử lý anomalies**:

   ```
   Dựa trên dataset này, hãy giúp tôi:
   1. Xác định các outliers trong các metrics (story points, cycle time)
   2. Phát hiện các inconsistencies trong dữ liệu (ví dụ: issues có dates không hợp lệ)
   3. Đề xuất cách xử lý các anomalies này (remove, replace, flag)

   [Dán dữ liệu cần làm sạch]
   ```

2. **Standardization và Normalization**:

   ```
   Hãy giúp tôi chuẩn hóa dữ liệu sau:
   1. Convert các định dạng ngày giờ khác nhau thành một định dạng nhất quán
   2. Normalize các trường text (status, priority, resolution)
   3. Đề xuất các calculated fields hữu ích cho phân tích

   [Dán dữ liệu cần chuẩn hóa]
   ```

#### Data Transformation

Biến đổi dữ liệu để phù hợp với phân tích:

1. **Aggregation và Summarization**:

   - Nhóm dữ liệu theo sprint, assignee, component...
   - Tính toán các chỉ số tổng hợp (mean, median, percentiles)

2. **Feature Engineering**:

   - Tạo các chỉ số mới từ dữ liệu gốc
   - Ví dụ: Cycle time, Lead time, Escaped defects ratio...

3. **Time Series Preparation**:
   - Đảm bảo dữ liệu theo thời gian được sắp xếp đúng
   - Xử lý missing values trong time series

### 3. Phân tích và trích xuất insights

#### Statistical Analysis

1. **Descriptive Statistics**:

   ```
   Dựa trên dữ liệu sprint metrics này, hãy tính toán và giải thích:
   1. Mean, median và standard deviation của velocity
   2. Distribution của story points estimates
   3. Correlation giữa estimates và actual effort
   4. Trends và seasonality trong team performance

   [Dán dữ liệu sprint metrics]
   ```

2. **Comparative Analysis**:

   ```
   Hãy so sánh hiệu suất giữa 2 teams/projects dựa trên dữ liệu sau:
   1. Velocity và stability
   2. Defect rates và quality metrics
   3. Cycle time và predictability
   4. Highlight điểm mạnh và điểm yếu của mỗi team/project

   [Dán dữ liệu so sánh]
   ```

#### Pattern Recognition

1. **Issue Flow Patterns**:

   ```
   Phân tích flow của issues qua các trạng thái và xác định:
   1. Common flow paths (các đường đi phổ biến nhất của issues)
   2. Bottleneck states (trạng thái có thời gian dừng lâu nhất)
   3. Rework patterns (issues quay trở lại trạng thái trước)
   4. Seasonal patterns trong flow (theo thời gian trong sprint/tháng)

   [Dán dữ liệu issue transitions]
   ```

2. **Team Behavior Analysis**:

   ```
   Phân tích hành vi làm việc của team dựa trên dữ liệu:
   1. Peak productivity periods
   2. Collaboration patterns (dựa trên PR reviews, comments)
   3. Response time đối với các issues khác nhau
   4. Working patterns (thời gian commit, update issues)

   [Dán dữ liệu team activity]
   ```

#### Predictive Analytics

1. **Delivery Forecast**:

   ```
   Dựa trên lịch sử velocity và scope hiện tại, hãy dự báo:
   1. Số sprint cần thiết để hoàn thành backlog
   2. Confidence intervals cho dự báo
   3. Risk factors có thể ảnh hưởng đến timeline
   4. Đề xuất adjustments để đạt deadline

   [Dán dữ liệu velocity history và backlog]
   ```

2. **Quality Prediction**:

   ```
   Dựa trên metrics về code và testing, hãy dự đoán:
   1. Expected defect rate cho các components
   2. Areas có risk cao nhất về quality issues
   3. Impact của technical debt lên future development
   4. Đề xuất prevention measures cho high-risk areas

   [Dán dữ liệu code quality và testing]
   ```

### 4. Tạo báo cáo và visualizations

#### Report Structure Design

Cấu trúc báo cáo hiệu quả:

1. **Executive Summary**:

   - 1-2 paragraphs tóm tắt findings chính
   - Highlight các metrics quan trọng nhất
   - Callout recommendations ưu tiên cao

2. **Detailed Analysis**:

   - Phân chia theo chủ đề/vấn đề
   - Sử dụng subheadings rõ ràng
   - Cân bằng giữa depth và clarity

3. **Recommendations Section**:
   - Actions cụ thể, khả thi
   - Prioritization rõ ràng
   - Expected outcomes
   - Measurement plan

#### AI-assisted Visualization Design

Sử dụng AI để thiết kế các visualization hiệu quả:

```
Dựa trên dữ liệu sau đây, hãy đề xuất 3-5 visualizations hiệu quả nhất để truyền đạt insights chính:
1. Mô tả chi tiết mỗi visualization (loại biểu đồ, data mapping)
2. Giải thích insight mà visualization giúp highlight
3. Đề xuất color scheme và annotations quan trọng
4. Đề xuất cách sắp xếp các visualizations trong dashboard

[Dán dữ liệu cần visualize]
```

## So sánh kết quả phân tích thủ công và sử dụng AI

### 1. Tốc độ và hiệu quả

#### Time Comparison Exercise

Thực hiện một bài tập so sánh:

1. **Phân tích thủ công**:

   - Theo dõi thời gian thực hiện một phân tích cụ thể (ví dụ: velocity trend analysis)
   - Ghi lại các bước và công cụ sử dụng (Excel, Jira reports)

2. **Phân tích với AI**:

   - Thực hiện cùng phân tích với sự hỗ trợ của AI
   - Ghi lại prompt, thời gian, và kết quả

3. **So sánh**:
   - Thời gian hoàn thành
   - Số lượng steps
   - Cognitive load (độ phức tạp tư duy)

#### Productivity Enhancement Strategies

Thảo luận các chiến lược để tối ưu hóa productivity khi kết hợp phân tích thủ công và AI:

1. Các task phù hợp nhất cho AI
2. Các task cần human judgment
3. Workflow để kết hợp cả hai approach

### 2. Độ chính xác và tin cậy

#### Accuracy Assessment

Đánh giá độ chính xác của phân tích AI:

1. **Validation Process**:

   - So sánh kết quả AI với ground truth
   - Xác định các loại sai sót phổ biến

2. **Factors Affecting Accuracy**:
   - Chất lượng dữ liệu đầu vào
   - Đặc thù dự án không được capture trong data
   - Độ phức tạp của phân tích

#### Trust Building Techniques

Xây dựng sự tin cậy vào kết quả phân tích AI:

1. Transparency trong phương pháp phân tích
2. Kết hợp domain expertise để validate
3. Nêu rõ confidence levels và limitations
4. Cung cấp evidence cho conclusions

### 3. Khả năng phát hiện pattern phức tạp

#### Complex Pattern Recognition Case Study

Thực hiện case study về nhận diện pattern phức tạp:

1. **Scenario**:

   - Multi-dimensional correlations trong project data
   - Subtle trends khó nhận diện bằng mắt thường

2. **AI Analysis**:

   ```
   Hãy phân tích dataset này và tìm các correlations và patterns ẩn giữa:
   1. Team composition và defect rates
   2. Sprint planning accuracy và delivery success
   3. Communication patterns (từ comments) và issue resolution time
   4. Technical complexity và team velocity

   Tìm kiếm cả direct correlations và subtle patterns.

   [Dán multi-dimensional dataset]
   ```

3. **Human Expert Analysis**:
   - Domain expert phân tích cùng dataset
   - So sánh findings

#### AI Limitations

Thảo luận về limitations của AI trong phân tích phức tạp:

1. Causation vs. Correlation confusion
2. Historical bias trong data
3. Thiếu context ngoài dữ liệu
4. Over-confidence trong predictions

## Các kỹ thuật nâng cao

### 1. Kết hợp nhiều loại dữ liệu

#### Multi-source Data Integration

Thực hành kết hợp dữ liệu từ nhiều nguồn:

```
Tôi có dữ liệu từ 3 nguồn khác nhau: Jira, Git repository, và Confluence. Hãy giúp tôi:

1. Xác định common keys để join dữ liệu (ví dụ: issue keys, dates, users)
2. Đề xuất cách kết hợp dữ liệu để phân tích toàn diện hơn
3. Tạo một data model tích hợp nhiều nguồn
4. Highlight insights mới có được từ việc kết hợp dữ liệu

Jira data: [Mẫu dữ liệu Jira]
Git data: [Mẫu dữ liệu Git]
Confluence data: [Mẫu dữ liệu Confluence]
```

#### Contextual Analysis

Phân tích có context từ nhiều nguồn:

1. Kết hợp commit messages với Jira tickets
2. Enriching issue data với meeting notes từ Confluence
3. Cross-referencing PR comments với issue discussions

### 2. Phân tích xu hướng dài hạn

#### Long-term Trend Detection

Phát hiện và phân tích xu hướng dài hạn:

```
Tôi có dữ liệu dự án trải dài qua 18 tháng (12 sprints). Hãy phân tích:

1. Long-term trends trong velocity, quality, và team health
2. Seasonal patterns (ví dụ: ảnh hưởng của holidays, quarter end)
3. Impact của major events (ví dụ: team changes, process changes)
4. Progress toward strategic goals (cải thiện lead time, quality)

[Dán dữ liệu dự án dài hạn]
```

#### Maturity Model Analysis

Phân tích sự trưởng thành của team/process theo thời gian:

1. Process maturity indicators
2. Team capability evolution
3. Tốc độ adoption các practices mới
4. Growth patterns trong team dynamics

### 3. Dự báo tiến độ và rủi ro dự án

#### Predictive Modeling Techniques

Kỹ thuật dự báo tiến độ:

```
Dựa trên lịch sử các sprints trước và current backlog, hãy xây dựng một predictive model để:

1. Dự báo completion date với confidence intervals
2. Xác định key risk factors ảnh hưởng đến timeline
3. Phân tích sensitivity của prediction đối với các biến số
4. Đề xuất adjustments để tăng confidence trong timeline

[Dán dữ liệu lịch sử sprint và backlog]
```

#### Risk Prediction and Mitigation

Dự báo và giảm thiểu rủi ro:

1. Early warning indicators
2. Risk probability assessment
3. Impact analysis
4. Mitigation strategy recommendations

## Workshop Closing Exercise

### Multi-scenario Analysis Challenge

Để kết thúc workshop, học viên sẽ thực hiện một thử thách phân tích đa kịch bản:

1. **Dataset**: Full project data từ một dự án thực tế (đã ẩn danh)

2. **Challenge**:

   - Đóng vai trò consultant phân tích dự án
   - Xác định 3 vấn đề lớn nhất ảnh hưởng đến hiệu suất
   - Tạo một executive report tóm tắt findings
   - Đề xuất action plan chi tiết

3. **Presentation**:
   - Trình bày findings trong một "mock client meeting"
   - Nhận và trả lời feedback
   - Cải tiến phân tích dựa trên feedback

### Reflection và Action Plan

Kết thúc module với phần reflection:

1. **Knowledge Assessment**:

   - Kiến thức mới về phân tích dữ liệu
   - Kỹ năng sử dụng AI cho phân tích
   - Gaps cần tiếp tục học hỏi

2. **Personal Action Plan**:
   - 3 techniques để áp dụng ngay
   - Resources để tiếp tục học hỏi
   - Next steps trong hành trình AI-assisted analysis

## Tài liệu tham khảo và đọc thêm

- [DORA Metrics: Measuring and Improving Software Delivery](https://cloud.google.com/blog/products/devops-sre/using-the-four-keys-to-measure-your-devops-performance)
- [The Art of Agile Development by James Shore](https://www.jamesshore.com/v2/books/aoad2)
- [Data-Driven Agile Transformation by David Bulkin](https://www.datadriven-agile.com/)
- [Accelerate: Building and Scaling High Performing Technology Organizations by Nicole Forsgren PhD, Jez Humble, and Gene Kim](https://itrevolution.com/product/accelerate/)
- [Flow Framework Resources](https://flowframework.org/resources/)
- Online courses: Advanced Data Analysis in Agile Teams
