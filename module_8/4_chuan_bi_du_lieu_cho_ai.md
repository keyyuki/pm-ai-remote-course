# Chuẩn bị dữ liệu để đưa cho AI

## 1. Tầm quan trọng của việc chuẩn bị dữ liệu cho AI

Khi sử dụng AI để phân tích dữ liệu dự án, **chất lượng đầu vào quyết định chất lượng đầu ra** (garbage in, garbage out). Việc chuẩn bị dữ liệu tốt giúp:

- **Tăng độ chính xác** của phân tích và dự báo
- **Tránh hiểu sai** và kết luận không chính xác
- **Tối ưu hóa token** khi sử dụng các mô hình AI (như GPT, Gemini)
- **Tiết kiệm thời gian** do không phải yêu cầu AI làm rõ hoặc phân tích lại
- **Nâng cao khả năng** phát hiện insight có giá trị

## 2. Làm sạch và chuẩn hóa dữ liệu

### 2.1. Xử lý dữ liệu thiếu hoặc không đồng nhất

#### 2.1.1. Phát hiện dữ liệu thiếu

Python code để kiểm tra dữ liệu thiếu trong Pandas DataFrame:

```python
import pandas as pd

# Đọc dữ liệu
jira_data = pd.read_csv('jira_export.csv')

# Kiểm tra giá trị thiếu
missing_values = jira_data.isnull().sum()
print("Số lượng giá trị thiếu trong mỗi cột:")
print(missing_values)

# Tỷ lệ giá trị thiếu
missing_percentage = (missing_values / len(jira_data)) * 100
print("\nTỷ lệ giá trị thiếu (%):")
print(missing_percentage)
```

#### 2.1.2. Chiến lược xử lý dữ liệu thiếu

| Loại dữ liệu     | Chiến lược xử lý                    | Ví dụ                                                                  |
| ---------------- | ----------------------------------- | ---------------------------------------------------------------------- |
| Story points     | Điền bằng giá trị trung bình/median | `df['story_points'].fillna(df['story_points'].median(), inplace=True)` |
| Assignee         | Đánh dấu là "Unassigned"            | `df['assignee'].fillna('Unassigned', inplace=True)`                    |
| Dates            | Loại bỏ hoặc đánh dấu đặc biệt      | `df = df.dropna(subset=['created_date'])`                              |
| Categorical data | Tạo category mới "Unknown"          | `df['priority'].fillna('Unknown', inplace=True)`                       |

#### 2.1.3. Xử lý dữ liệu không đồng nhất

```python
# Chuẩn hóa trạng thái
df['status'] = df['status'].str.lower().str.strip()
df['status'] = df['status'].replace({
    'in progress': 'In Progress',
    'in-progress': 'In Progress',
    'inprogress': 'In Progress',
    'done': 'Done',
    'closed': 'Done',
    'resolved': 'Done'
})

# Chuẩn hóa tên người dùng
df['assignee'] = df['assignee'].str.lower().str.strip()
df['assignee'] = df['assignee'].replace({
    'j.smith': 'John Smith',
    'john.s': 'John Smith',
    'john.smith': 'John Smith'
})
```

### 2.2. Loại bỏ thông tin nhạy cảm hoặc không liên quan

#### 2.2.1. Nhận diện thông tin nhạy cảm

Các loại thông tin nhạy cảm thường gặp:

- Thông tin cá nhân (email, số điện thoại)
- Mật khẩu, tokens, API keys
- Thông tin khách hàng riêng tư
- Dữ liệu tài chính, lương thưởng
- Phản hồi nội bộ hoặc đánh giá tiêu cực

#### 2.2.2. Kỹ thuật ẩn danh hóa

```python
import re

# Ẩn danh email
df['comment'] = df['comment'].apply(
    lambda x: re.sub(r'[\w\.-]+@[\w\.-]+', '[EMAIL REDACTED]', str(x))
)

# Ẩn danh số điện thoại
df['description'] = df['description'].apply(
    lambda x: re.sub(r'\b(?:\d{3}[-.\s]?)?\d{3}[-.\s]?\d{4}\b',
                     '[PHONE REDACTED]', str(x))
)

# Thay thế tên người thật bằng mã
user_mapping = {
    'John Smith': 'User001',
    'Jane Doe': 'User002'
}
df['assignee'] = df['assignee'].map(user_mapping).fillna(df['assignee'])
```

#### 2.2.3. Loại bỏ thông tin không liên quan

```python
# Loại bỏ các cột không cần thiết
columns_to_drop = ['internal_id', 'created_by_account_id', 'avatar_url']
df = df.drop(columns=columns_to_drop)

# Lọc bỏ comments tự động từ hệ thống
df['comments'] = df['comments'].apply(
    lambda x: [c for c in x if not c.startswith('Automatic comment:')]
    if isinstance(x, list) else x
)
```

### 2.3. Chuẩn hóa định dạng ngày tháng, tên người dùng

#### 2.3.1. Chuẩn hóa ngày tháng

```python
import pandas as pd
from datetime import datetime

# Chuyển đổi cột ngày thành định dạng chuẩn
df['created_date'] = pd.to_datetime(df['created_date'], errors='coerce')
df['updated_date'] = pd.to_datetime(df['updated_date'], errors='coerce')

# Format ngày tháng theo tiêu chuẩn ISO
df['created_date_iso'] = df['created_date'].dt.strftime('%Y-%m-%d')

# Tính toán thời gian giữa hai sự kiện (ví dụ: thời gian giải quyết)
df['resolution_days'] = (df['resolved_date'] - df['created_date']).dt.days
```

#### 2.3.2. Chuẩn hóa tên người dùng và các trường văn bản

```python
# Loại bỏ khoảng trắng thừa và chuyển về lowercase
df['assignee'] = df['assignee'].str.strip().str.lower()

# Áp dụng mapping cho tên người dùng
username_mapping = {
    'john': 'John Smith',
    'john.smith': 'John Smith',
    'j.smith': 'John Smith',
    'jane': 'Jane Doe',
    'jane.doe': 'Jane Doe',
    'j.doe': 'Jane Doe'
}
df['assignee'] = df['assignee'].map(username_mapping).fillna(df['assignee'])

# Chuẩn hóa các giá trị categorical
df['priority'] = df['priority'].str.title()  # 'high' -> 'High'
```

## 3. Cấu trúc dữ liệu phù hợp với khả năng nhập của các công cụ AI

### 3.1. Định dạng JSON, CSV, hoặc văn bản có cấu trúc

#### 3.1.1. JSON - Linh hoạt, dễ đọc cho AI

```json
{
  "project_info": {
    "name": "Project X",
    "key": "PROJ",
    "start_date": "2024-01-15",
    "end_date": "2024-06-30"
  },
  "sprint_data": {
    "sprint_name": "Sprint 5",
    "start_date": "2024-04-01",
    "end_date": "2024-04-14",
    "completed_story_points": 34,
    "total_story_points": 40
  },
  "issues": [
    {
      "key": "PROJ-123",
      "summary": "Implement user authentication",
      "status": "Done",
      "type": "Story",
      "story_points": 5,
      "assignee": "Jane Doe",
      "created_date": "2024-03-25",
      "resolved_date": "2024-04-10",
      "commits": [
        {
          "hash": "3c4e9cd",
          "author": "Jane Doe",
          "date": "2024-04-03",
          "message": "Add login form and validation"
        },
        {
          "hash": "7a2b9f1",
          "author": "Jane Doe",
          "date": "2024-04-07",
          "message": "Implement OAuth integration"
        }
      ]
    }
  ]
}
```

#### 3.1.2. CSV - Đơn giản, tabular data

```
key,summary,status,type,story_points,assignee,created_date,resolved_date
PROJ-123,Implement user authentication,Done,Story,5,Jane Doe,2024-03-25,2024-04-10
PROJ-124,Fix login button on mobile,Done,Bug,2,John Smith,2024-03-27,2024-04-05
PROJ-125,Create user profile page,In Progress,Story,8,Alex Johnson,2024-03-28,
```

#### 3.1.3. Văn bản có cấu trúc - Dễ đọc cho cả con người và AI

```
## Project Summary: Project X
Start Date: 2024-01-15
End Date: 2024-06-30
Total Sprints: 12
Current Sprint: Sprint 5 (2024-04-01 to 2024-04-14)

## Sprint 5 Statistics
Completed Stories: 7/8
Completed Story Points: 34/40
Bugs Resolved: 5
New Bugs Reported: 3

## Top Issues
1. PROJ-123: Implement user authentication
   - Type: Story
   - Status: Done
   - Assignee: Jane Doe
   - Created: 2024-03-25
   - Resolved: 2024-04-10
   - Story Points: 5
   - Commits: 2

2. PROJ-124: Fix login button on mobile
   - Type: Bug
   - Status: Done
   - Assignee: John Smith
   - Created: 2024-03-27
   - Resolved: 2024-04-05
   - Story Points: 2
   - Commits: 1
```

### 3.2. Phân chia dữ liệu thành các phần dễ tiêu hóa

#### 3.2.1. Nhóm dữ liệu theo context logic

Thay vì gửi toàn bộ dữ liệu, hãy nhóm theo các chủ đề:

- **Tổng quan dự án**: Thông tin cơ bản, tiến độ tổng thể
- **Sprint hiện tại**: Chi tiết về sprint đang diễn ra
- **Issues theo trạng thái**: Các issues đã hoàn thành, đang tiến hành, bị chặn
- **Issues theo loại**: Bugs, User Stories, Tasks
- **Phân tích xu hướng**: So sánh với các sprint trước đó

#### 3.2.2. Sử dụng hierarchy và đánh số

Tổ chức thông tin theo cấu trúc phân cấp rõ ràng:

```
# Báo cáo Sprint 5 - Project X

## 1. Tổng quan Sprint
   1.1. Thời gian: 2024-04-01 đến 2024-04-14
   1.2. Story Points: 34/40 hoàn thành (85%)
   1.3. Issues: 12/15 hoàn thành (80%)

## 2. Phân tích User Stories
   2.1. US-1: Authentication System
      2.1.1. Trạng thái: Done
      2.1.2. Story Points: 5
      2.1.3. Commits: 2

   2.2. US-2: User Profile Page
      2.2.1. Trạng thái: In Progress
      2.2.2. Story Points: 8
      2.2.3. Commits: 3

## 3. Phân tích Bugs
   3.1. Bugs đã giải quyết: 5
   3.2. Bugs mới phát sinh: 3
   3.3. Bug ưu tiên cao nhất: PROJ-128 (UI breaks on mobile)
```

## 4. Tạo context rõ ràng cho AI

### 4.1. Thêm mô tả về ý nghĩa của dữ liệu

Bắt đầu bằng việc giải thích dữ liệu và cung cấp definitions:

```
# Dữ liệu Sprint từ dự án "Customer Portal" (PROJ)

## Definitions:
- Story Points: Đơn vị đo độ phức tạp, 1 point ≈ 4 giờ làm việc
- Velocity: Tổng story points hoàn thành trong một sprint
- Cycle Time: Thời gian trung bình từ lúc bắt đầu làm đến khi hoàn thành
- Bugs Escaped: Bugs được phát hiện sau khi feature đã được deploy

## Thông tin Sprint:
Sprint 5 (01/04/2024 - 14/04/2024) là sprint thứ 5 trong roadmap phát triển Customer Portal. Mục tiêu chính của sprint này là hoàn thiện tính năng authentication và user profile management.
```

### 4.2. Cung cấp thông tin nền tảng về dự án

```
# Thông tin nền về dự án Customer Portal

## Tổng quan dự án:
- Loại dự án: Web application
- Công nghệ: React frontend, Node.js backend, MongoDB
- Team: 5 developers, 1 QA, 1 Designer, 1 Product Owner, 1 Scrum Master
- Methodology: Scrum với 2-week sprints
- Timeline: 6 tháng (Tháng 1/2024 - Tháng 6/2024)

## Business context:
Dự án Customer Portal nhằm thay thế hệ thống portal cũ đã 5 năm tuổi. Mục tiêu chính là tăng customer engagement 30% và giảm 50% support tickets nhờ self-service features.

## Thách thức hiện tại:
- Team mới chỉ đạt 80% planned velocity trong các sprint trước
- Có sự phụ thuộc vào API bên thứ 3 đang gây chậm trễ
- Đã phát hiện performance issues trên mobile devices
```

### 4.3. Định rõ mục tiêu phân tích

```
# Yêu cầu phân tích

## Mục tiêu chính:
Phân tích dữ liệu Sprint 5 để xác định nguyên nhân của việc không đạt được 100% planned velocity và đưa ra các đề xuất cải thiện cho Sprint 6.

## Câu hỏi cụ thể cần trả lời:
1. Đâu là những bottlenecks chính ảnh hưởng đến tiến độ?
2. Các user stories nào mất nhiều thời gian hơn dự kiến và tại sao?
3. Pattern nào xuất hiện trong việc phân bổ công việc giữa các team members?
4. Có mối tương quan nào giữa story points estimate và thời gian thực tế?
5. Những cải thiện nào có thể áp dụng cho sprint tiếp theo?

## Đầu ra mong muốn:
- Phân tích ngắn gọn về hiệu suất Sprint 5
- Top 3 nguyên nhân của việc không đạt kế hoạch
- 3-5 đề xuất cụ thể cho Sprint 6
```

## 5. Kỹ thuật "chunking" dữ liệu lớn

### 5.1. Tại sao cần chia nhỏ dữ liệu?

Các mô hình AI như GPT, Gemini, Claude đều có giới hạn về số lượng tokens có thể xử lý trong một lần:

- **GPT-4**: khoảng 8,000 - 32,000 tokens
- **GPT-3.5**: khoảng 4,000 tokens
- **Gemini Pro**: khoảng 32,000 tokens
- **Claude**: khoảng 100,000 tokens

Dữ liệu dự án thường rất lớn, vượt quá giới hạn này, do đó cần chiến lược "chunking" hợp lý.

### 5.2. Chiến lược chia nhỏ dữ liệu

#### 5.2.1. Phân loại theo mức độ chi tiết

```
# Chunking theo 3 mức độ chi tiết

## Chunk 1: Tổng quan dự án và sprint (High-level)
- Tên dự án, timeline, team
- Mục tiêu sprint, KPIs
- Tóm tắt tiến độ

## Chunk 2: Phân tích theo nhóm (Mid-level)
- User Stories theo epic/feature
- Bugs theo mức độ ưu tiên
- Commit activity theo component

## Chunk 3: Chi tiết cụ thể (Low-level)
- Phân tích chi tiết từng User Story
- Chi tiết thay đổi code (diff, commits)
- Thời gian chi tiết cho từng task
```

#### 5.2.2. Phân loại theo chủ đề

```
# Chunking theo chủ đề

## Chunk 1: Dữ liệu Jira
- Sprint metrics
- Issue details
- Worklog data

## Chunk 2: Dữ liệu Git
- Commit history
- Branch information
- Code change statistics

## Chunk 3: Dữ liệu liên kết
- Mapping giữa Jira issues và Git commits
- Timeline tích hợp
- Phân tích cross-system
```

#### 5.2.3. Phân loại theo mục tiêu phân tích

```
# Chunking theo mục tiêu phân tích

## Chunk 1: Phân tích hiệu suất team
- Velocity và capacity
- Workload distribution
- Expertise areas

## Chunk 2: Phân tích chất lượng
- Bug rate và severity
- Code review feedback
- Test coverage

## Chunk 3: Phân tích quy trình
- Cycle time và lead time
- Bottlenecks
- Workflow efficiency
```

### 5.3. Kỹ thuật reference và summary

Khi dữ liệu quá lớn, có thể sử dụng:

1. **Summary with references**: Cung cấp tóm tắt với tham chiếu đến chi tiết
2. **Progressive disclosure**: Bắt đầu với high-level, sau đó đi vào chi tiết khi AI yêu cầu
3. **Sample-based analysis**: Sử dụng mẫu đại diện thay vì toàn bộ dữ liệu

Ví dụ:

```
# Sprint 5 Analysis - Summary

## Overview metrics:
- 15 issues total (8 Stories, 5 Bugs, 2 Tasks)
- 40 story points planned, 34 completed (85%)
- 98 commits across 12 branches

## Key issues that impacted velocity:
1. PROJ-123: Authentication System (5 SP)
   - Completed late due to third-party API issues
   - Details available in Issue Details Chunk if needed

2. PROJ-128: Mobile UI Bug (3 SP)
   - Required unexpected refactoring
   - Details available in Bug Analysis Chunk if needed

## Team performance patterns:
- Backend team achieved 92% of planned points
- Frontend team achieved 78% of planned points
- Details on individual performance available in Team Analysis Chunk if needed
```

## 6. Thực hành chuẩn bị một bộ dữ liệu mẫu để AI phân tích

### Tình huống: Phân tích hiệu suất Sprint để cải thiện kế hoạch tương lai

#### Yêu cầu:

- Chuẩn bị dữ liệu cho AI phân tích một sprint vừa kết thúc
- Mục tiêu là xác định vấn đề và cải thiện cho sprint tiếp theo
- Các nguồn dữ liệu bao gồm Jira, Git, và biên bản họp

#### Các bước thực hiện:

1. **Thu thập dữ liệu thô**:

   - Export sprint data từ Jira
   - Export commit history từ Git repository
   - Lấy nội dung biên bản họp từ Confluence

2. **Làm sạch và chuẩn hóa dữ liệu**:

   ```python
   # Giả sử đã load dữ liệu vào DataFrames: jira_df, git_df

   # Xử lý dữ liệu thiếu
   jira_df['story_points'] = jira_df['story_points'].fillna(0)
   jira_df['assignee'] = jira_df['assignee'].fillna('Unassigned')

   # Chuẩn hóa ngày tháng
   jira_df['created'] = pd.to_datetime(jira_df['created'])
   jira_df['resolved'] = pd.to_datetime(jira_df['resolved'])

   # Tính cycle time
   jira_df['cycle_time_days'] = (jira_df['resolved'] - jira_df['started']).dt.days

   # Liên kết Git với Jira
   git_df['issue_key'] = git_df['commit_message'].str.extract(r'(PROJ-\d+)')
   ```

3. **Cấu trúc dữ liệu theo chủ đề**:

   ```python
   # Tạo summary DataFrame
   summary = {
       "project_name": "Customer Portal",
       "sprint_name": "Sprint 5",
       "sprint_dates": "2024-04-01 to 2024-04-14",
       "planned_story_points": jira_df['story_points'].sum(),
       "completed_story_points": jira_df[jira_df['status'] == 'Done']['story_points'].sum(),
       "completion_rate": f"{(jira_df[jira_df['status'] == 'Done']['story_points'].sum() / jira_df['story_points'].sum()) * 100:.1f}%",
       "issues_total": len(jira_df),
       "issues_completed": len(jira_df[jira_df['status'] == 'Done']),
       "commits_total": len(git_df)
   }

   # Issues by type
   issues_by_type = jira_df.groupby('issue_type').agg({
       'key': 'count',
       'story_points': 'sum'
   }).reset_index().rename(columns={'key': 'count'})

   # Issues by assignee
   issues_by_assignee = jira_df.groupby('assignee').agg({
       'key': 'count',
       'story_points': 'sum',
       'cycle_time_days': 'mean'
   }).reset_index().rename(columns={'key': 'count'})
   ```

4. **Tạo context rõ ràng**:

   ```python
   context = f"""
   # Sprint 5 Analysis - Customer Portal Project

   ## Definitions
   - Story Points: Measure of complexity, 1 point ≈ 4 hours of work
   - Cycle Time: Days from "In Progress" to "Done"
   - Completion Rate: % of planned story points completed

   ## Project Context
   Customer Portal is a web application being developed to replace a legacy system.
   The team consists of 5 developers, 1 QA, 1 designer working in 2-week Scrum sprints.
   This is Sprint 5 out of a planned 12 sprints total.

   ## Analysis Objective
   The team wants to understand why they've been consistently missing sprint goals
   (completing ~85% of planned story points) and how to improve planning accuracy
   for upcoming sprints.
   """
   ```

5. **Chuyển đổi thành dạng dễ đọc cho AI**:

   ````python
   import json

   # Convert to dictionaries and then to JSON
   summary_json = json.dumps(summary, indent=2)
   issues_by_type_json = issues_by_type.to_dict(orient='records')
   issues_by_type_json = json.dumps(issues_by_type_json, indent=2)
   issues_by_assignee_json = issues_by_assignee.to_dict(orient='records')
   issues_by_assignee_json = json.dumps(issues_by_assignee_json, indent=2)

   # Top issues with details
   top_issues = jira_df.sort_values('story_points', ascending=False).head(5)
   top_issues_json = top_issues.to_dict(orient='records')
   top_issues_json = json.dumps(top_issues_json, indent=2)

   # Combine all data into a structured format
   ai_ready_data = f"""
   {context}

   ## Sprint Summary
   ```json
   {summary_json}
   ````

   ## Issues by Type

   ```json
   {issues_by_type_json}
   ```

   ## Team Member Performance

   ```json
   {issues_by_assignee_json}
   ```

   ## Top 5 Issues by Story Points

   ```json
   {top_issues_json}
   ```

   """

   ```

   ```

6. **Chunkify nếu cần thiết**:

   ````python
   # Kiểm tra độ dài và chia chunk nếu cần
   import tiktoken

   def count_tokens(text):
       enc = tiktoken.encoding_for_model("gpt-4")
       return len(enc.encode(text))

   token_count = count_tokens(ai_ready_data)
   print(f"Token count: {token_count}")

   # Nếu quá lớn, chia thành nhiều chunks
   if token_count > 6000:  # Giả sử giới hạn an toàn là 6000 tokens
       chunks = [
           context + "\n\n## Sprint Summary\n```json\n" + summary_json + "\n```",
           "## Issues by Type\n```json\n" + issues_by_type_json + "\n```",
           "## Team Member Performance\n```json\n" + issues_by_assignee_json + "\n```",
           "## Top 5 Issues by Story Points\n```json\n" + top_issues_json + "\n```"
       ]

       for i, chunk in enumerate(chunks):
           print(f"Chunk {i+1} token count: {count_tokens(chunk)}")
   ````

7. **Chuẩn bị prompt cho AI**:

   ```
   Dựa vào dữ liệu Sprint 5 của dự án Customer Portal được cung cấp dưới đây, hãy:

   1. Phân tích nguyên nhân khiến team chỉ hoàn thành 85% công việc đã lên kế hoạch
   2. Xác định các pattern và xu hướng liên quan đến hiệu suất team
   3. Đề xuất 3-5 cải thiện cụ thể để tăng độ chính xác trong planning cho Sprint 6
   4. Xác định các rủi ro tiềm ẩn có thể ảnh hưởng đến Sprint 6

   Dữ liệu Sprint:
   {ai_ready_data}
   ```

## 7. Best practices và lưu ý khi chuẩn bị dữ liệu

### 7.1. Đảm bảo tính nhất quán

- **Sử dụng định dạng chuẩn**: Chọn một định dạng nhất quán (ISO dates, naming conventions)
- **Áp dụng quy tắc đồng bộ**: Đảm bảo mapping giữa các hệ thống (Jira IDs trong Git commits)
- **Làm rõ hệ thống đo lường**: Giải thích rõ ràng quy ước (story points, priority levels)

### 7.2. Tập trung vào relevant data

- **Loại bỏ noise**: Chỉ giữ thông tin liên quan đến mục tiêu phân tích
- **Nhấn mạnh key metrics**: Đặt thông tin quan trọng ở vị trí nổi bật
- **Provide contextual relationships**: Làm rõ mối quan hệ giữa các phần dữ liệu

### 7.3. Khắc phục thiên kiến trong dữ liệu

- **Cảnh báo về outliers**: Nêu rõ các điểm dữ liệu bất thường
- **Giải thích các yếu tố ngoại cảnh**: Ví dụ như ngày lễ, sự kiện đặc biệt
- **Cân nhắc historical patterns**: So sánh với dữ liệu lịch sử để đặt trong ngữ cảnh

### 7.4. Đánh giá chất lượng dữ liệu

Trước khi đưa cho AI, tự hỏi:

1. **Completeness**: Dữ liệu có đủ để đưa ra kết luận không?
2. **Accuracy**: Dữ liệu có chính xác và đáng tin cậy không?
3. **Relevance**: Dữ liệu có liên quan đến vấn đề cần giải quyết không?
4. **Timeliness**: Dữ liệu có đủ mới để đưa ra quyết định không?
5. **Consistency**: Các định nghĩa và metrics có nhất quán không?

## Bài tập thực hành

1. Từ một file CSV export từ Jira (cung cấp mẫu), hãy viết script Python để:

   - Làm sạch dữ liệu (xử lý missing values, chuẩn hóa dates)
   - Tính toán các metrics chính (completion rate, cycle time, distribution)
   - Xuất ra một JSON file có cấu trúc phù hợp để đưa cho AI phân tích

2. Với một dataset mẫu về Git commits, hãy:

   - Phân tích và loại bỏ thông tin nhạy cảm (emails, potential secrets)
   - Tổ chức dữ liệu theo hierarchy dễ hiểu
   - Tạo summary phù hợp với giới hạn 4000 tokens

3. Kết hợp dữ liệu từ Jira và Git (mẫu được cung cấp) để:
   - Tạo timeline tích hợp của một sprint
   - Cấu trúc thành 3 chunks logic dựa trên mức độ chi tiết
   - Viết prompt phù hợp cho AI phân tích hiệu suất của sprint

## Tài liệu tham khảo

- [Python Data Cleaning Guide](https://realpython.com/python-data-cleaning-numpy-pandas/)
- [OpenAI Tokenizer](https://platform.openai.com/tokenizer) - công cụ hữu ích để kiểm tra số tokens
- [Data Anonymization Best Practices](https://www.imperva.com/learn/data-security/data-anonymization/)
- [JSON Structure Best Practices](https://google.github.io/styleguide/jsoncstyleguide.xml)
- [The Art of Prompt Engineering](https://eugeneyan.com/writing/prompt-engineering/)
