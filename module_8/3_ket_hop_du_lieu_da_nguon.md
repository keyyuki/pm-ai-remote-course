# Kết hợp dữ liệu từ các nguồn

## 1. Tại sao cần kết hợp dữ liệu từ nhiều nguồn?

Trong môi trường phát triển phần mềm hiện đại, thông tin về dự án thường được lưu trữ phân tán ở nhiều hệ thống khác nhau:

- **Jira**: Quản lý công việc, theo dõi tiến độ, bugs
- **Git**: Lịch sử phát triển, thay đổi code, commits
- **Confluence**: Tài liệu, yêu cầu, đặc tả kỹ thuật, hướng dẫn
- **Google Drive**: Tài liệu chia sẻ, báo cáo, bảng tính phân tích

Kết hợp dữ liệu từ các nguồn này mang lại nhiều lợi ích:

- **Bức tranh toàn cảnh**: Hiểu đầy đủ tình trạng dự án
- **Phân tích sâu**: Phát hiện mối tương quan giữa yêu cầu, tiến độ và thực thi
- **Dự báo chính xác**: Ước tính thời gian dự án tốt hơn dựa trên dữ liệu lịch sử
- **Cải thiện quy trình**: Xác định điểm nghẽn và cơ hội tối ưu hóa

## 2. Tham chiếu tài liệu từ Confluence/Google Drive

### 2.1. Xác định tài liệu quan trọng cần tham chiếu

Một số loại tài liệu thường cần kết hợp trong phân tích:

- **Tài liệu yêu cầu**: Giúp hiểu rõ mục tiêu ban đầu của chức năng
- **Đặc tả kỹ thuật**: Cung cấp chi tiết về cách thức triển khai
- **Biên bản họp**: Ghi lại quyết định và thay đổi yêu cầu
- **Tài liệu kiến trúc**: Mối quan hệ giữa các thành phần hệ thống
- **Kế hoạch sprint**: Cam kết ban đầu về công việc cần hoàn thành

### 2.2. Trích xuất thông tin từ Confluence

#### 2.2.1. Sử dụng Confluence API

Sử dụng Confluence REST API để trích xuất dữ liệu:

```python
import requests
import json

# Thiết lập thông tin kết nối
base_url = "https://your-domain.atlassian.net/wiki"
api_endpoint = "/rest/api/content/123456?expand=body.storage"
auth = ("email@example.com", "API_TOKEN")

# Gửi yêu cầu
response = requests.get(f"{base_url}{api_endpoint}", auth=auth)
data = response.json()

# Trích xuất nội dung
content = data["body"]["storage"]["value"]
title = data["title"]
last_updated = data["version"]["when"]

print(f"Title: {title}")
print(f"Last updated: {last_updated}")
print(f"Content: {content[:100]}...")  # Hiển thị 100 ký tự đầu tiên
```

#### 2.2.2. Export trang Confluence về định dạng phù hợp

Các bước thực hiện:

1. Mở trang Confluence cần export
2. Click vào biểu tượng "..." (more actions)
3. Chọn "Export" và định dạng phù hợp (PDF, Word, HTML, XML)
4. Lưu file về máy để xử lý

### 2.3. Trích xuất thông tin từ Google Drive

#### 2.3.1. Sử dụng Google Drive API

Sử dụng Google Drive API và Google Sheets API để truy cập dữ liệu:

```python
from googleapiclient.discovery import build
from google.oauth2 import service_account

# Thiết lập xác thực
SCOPES = ['https://www.googleapis.com/auth/drive.readonly']
SERVICE_ACCOUNT_FILE = 'credentials.json'
credentials = service_account.Credentials.from_service_account_file(
    SERVICE_ACCOUNT_FILE, scopes=SCOPES)
drive_service = build('drive', 'v3', credentials=credentials)
sheets_service = build('sheets', 'v4', credentials=credentials)

# Lấy metadata của file
file_id = '1ABC123XYZ456'
file_metadata = drive_service.files().get(fileId=file_id).execute()
print(f"File name: {file_metadata.get('name')}")

# Lấy nội dung bảng tính
spreadsheet_id = '1DEF456UVW789'
range_name = 'Sheet1!A1:D10'
result = sheets_service.spreadsheets().values().get(
    spreadsheetId=spreadsheet_id, range=range_name).execute()
values = result.get('values', [])
print(f"Data: {values}")
```

#### 2.3.2. Export và download từ Google Drive

Các bước thực hiện:

1. Mở file Google Docs/Sheets cần export
2. Chọn File > Download
3. Chọn định dạng phù hợp (DOCX, XLSX, PDF, CSV)
4. Lưu file về máy để xử lý

## 3. Liên kết dữ liệu giữa Jira và Git

### 3.1. Sử dụng thông tin commit từ branch/PR liên kết với Jira issue

#### 3.1.1. Quy ước đặt tên nhánh và commit messages

Để tự động liên kết Git và Jira, cần tuân thủ quy ước đặt tên:

- **Branch name**: `type/JIRA-123-short-description`

  - Ví dụ: `feature/PROJ-456-add-user-authentication`

- **Commit messages**: `JIRA-123: Brief description of change`
  - Ví dụ: `PROJ-456: Implement login form and validation`

#### 3.1.2. Trích xuất commit liên quan đến Jira issue

```bash
# Tìm tất cả commit liên quan đến một issue
git log --grep="PROJ-456" --pretty=format:"%h,%an,%ad,%s" > PROJ-456_commits.csv

# Tìm tất cả branch liên quan
git branch -a | grep "PROJ-456"
```

#### 3.1.3. Sử dụng Development Panel trong Jira

Nếu Jira đã được tích hợp với Git/GitHub/Bitbucket:

1. Mở issue trong Jira
2. Xem tab "Development" hoặc panel "Development"
3. Xem danh sách commits, branches và PRs liên quan
4. Export thông tin này qua Jira API

### 3.2. Kết hợp thông tin tiến độ từ Jira với lịch sử thay đổi từ Git

#### 3.2.1. Xây dựng timeline tích hợp

Kết hợp dữ liệu để tạo timeline thể hiện:

1. **Thời điểm tạo issue** (từ Jira)
2. **Thời điểm bắt đầu làm việc** (từ Git - commit đầu tiên hoặc từ Jira - chuyển trạng thái)
3. **Tiến độ thực hiện** (các commits từ Git, thay đổi trạng thái từ Jira)
4. **Thời điểm hoàn thành** (từ Jira - chuyển sang Done, từ Git - commit cuối)

#### 3.2.2. Ví dụ Python script để kết hợp dữ liệu

```python
import pandas as pd
import matplotlib.pyplot as plt
from datetime import datetime

# Đọc dữ liệu đã export từ Jira và Git
jira_data = pd.read_csv("jira_issues.csv")
git_data = pd.read_csv("git_commits.csv")

# Chuẩn hóa cột issue key từ commit message
git_data['issue_key'] = git_data['message'].str.extract(r'(PROJ-\d+)')

# Kết hợp dữ liệu
combined_data = pd.merge(
    jira_data,
    git_data.groupby('issue_key').agg({
        'date': ['min', 'max', 'count'],
        'author': lambda x: ', '.join(x.unique())
    }),
    left_on='key',
    right_index=True,
    how='left'
)

# Phân tích và visualization
plt.figure(figsize=(12, 8))
plt.scatter(
    combined_data['created'],
    combined_data['date']['count'],
    alpha=0.7
)
plt.xlabel('Issue Created Date')
plt.ylabel('Number of Commits')
plt.title('Issue Complexity (Commits Count) vs Creation Date')
plt.tight_layout()
plt.savefig('issue_complexity_analysis.png')
```

## 4. Kết hợp tài liệu yêu cầu với dữ liệu triển khai

### 4.1. Mapping yêu cầu từ Confluence với User Stories trong Jira

| Confluence        | Jira               | Git                 |
| ----------------- | ------------------ | ------------------- |
| Tài liệu yêu cầu  | Epic, User Stories | Branches, Commits   |
| Đặc tả kỹ thuật   | Technical tasks    | Implementation code |
| Hướng dẫn sử dụng | Test cases         | Test implementation |

#### 4.1.1. Tạo ma trận truy xuất yêu cầu

Xây dựng bảng liên kết giữa:

- ID tài liệu yêu cầu trong Confluence
- Epic/Story ID trong Jira
- Branch/Commit trong Git

```
Yêu cầu REQ-001 (Confluence) -> Epic PROJ-100 (Jira) -> feature/PROJ-100-user-auth (Git)
  ├── User Story PROJ-101 -> feature/PROJ-101-login-form -> 5 commits
  ├── User Story PROJ-102 -> feature/PROJ-102-registration -> 8 commits
  └── User Story PROJ-103 -> feature/PROJ-103-password-reset -> 3 commits
```

### 4.2. Phân tích độ phức tạp và độ trễ

Bằng cách kết hợp dữ liệu từ ba nguồn, có thể phân tích:

1. **Độ phức tạp thực tế** so với ước tính:

   - Story Point từ Jira vs Số lượng commit từ Git
   - Lines of code changed từ Git vs Thời gian ước tính từ Jira

2. **Độ trễ** giữa yêu cầu và triển khai:
   - Thời điểm tài liệu yêu cầu được phê duyệt (Confluence)
   - Thời điểm User Story được tạo (Jira)
   - Thời điểm bắt đầu có commit (Git)
   - Thời điểm hoàn thành (Jira status + Git final commit)

## 5. Xây dựng bức tranh toàn cảnh về dự án

### 5.1. Kết hợp dữ liệu để trả lời câu hỏi kinh doanh quan trọng

- **Tốc độ phát triển có đạt kỳ vọng không?**

  - Sprint velocity từ Jira
  - Commit frequency từ Git
  - Thời gian thực hiện so với kế hoạch từ Confluence

- **Đâu là điểm nghẽn trong quy trình?**

  - Thời gian trung bình ở mỗi trạng thái từ Jira
  - Review time của PRs từ Git
  - Thời gian từ yêu cầu đến triển khai

- **Chất lượng code có đạt chuẩn không?**
  - Số lượng bugs từ Jira
  - Code review comments từ PRs
  - Test coverage từ CI/CD pipeline

### 5.2. Dashboard tích hợp

Xây dựng dashboard trực quan hiển thị dữ liệu từ nhiều nguồn:

1. **Tiến độ dự án**:

   - Burndown chart từ Jira
   - Commit activity từ Git
   - Milestone completion từ Confluence

2. **Chất lượng**:

   - Bug count và severity từ Jira
   - Code churn từ Git
   - Test coverage và test results

3. **Năng suất team**:
   - Story points completed từ Jira
   - Commit distribution từ Git
   - Documentation updates từ Confluence

## 6. Thực hành tạo báo cáo kết hợp dữ liệu từ nhiều nguồn

### Tình huống: Báo cáo tiến độ Sprint cho stakeholders

#### Yêu cầu:

- Tóm tắt tiến độ hoàn thành User Stories
- So sánh scope ban đầu với thực tế
- Phân tích điểm mạnh và điểm yếu trong sprint
- Dự báo khả năng hoàn thành cho sprint tiếp theo

#### Các nguồn dữ liệu:

1. **Jira**: Sprint report, issues completed/in progress
2. **Git**: Commit history, branch status
3. **Confluence**: Sprint planning document, acceptance criteria
4. **Google Drive**: Risk log, client feedback

#### Các bước thực hiện:

1. **Thu thập dữ liệu**:

   - Export sprint data từ Jira
   - Export commit history từ Git repository
   - Trích xuất sprint planning document từ Confluence
   - Download risk log và feedback từ Google Drive

2. **Chuẩn hóa dữ liệu**:

   - Chuyển tất cả timestamp sang cùng một múi giờ
   - Mapping giữa Jira issues và Git commits
   - Xác định các user story đã đáp ứng acceptance criteria

3. **Phân tích và tổng hợp**:

   - Tính tỷ lệ hoàn thành so với kế hoạch
   - Xác định user stories có nhiều thay đổi nhất
   - Phân tích mối tương quan giữa story points và số lượng commits

4. **Tạo báo cáo trực quan**:
   - Sprint progress chart với dữ liệu kết hợp
   - Issue status breakdown kèm thông tin từ Git
   - Timeline tích hợp từ tất cả các nguồn

## 7. Thách thức và giải pháp khi kết hợp dữ liệu

### 7.1. Thách thức phổ biến

1. **Thiếu tính nhất quán**:

   - User ID khác nhau giữa các hệ thống
   - Timestamp ở các múi giờ khác nhau
   - Cách đặt tên không thống nhất

2. **Dữ liệu không đồng bộ**:

   - Jira không được cập nhật kịp thời
   - Commit không tham chiếu đến Jira issue
   - Tài liệu trên Confluence đã lỗi thời

3. **Vấn đề quyền truy cập**:

   - Không đủ quyền để truy xuất dữ liệu đầy đủ
   - API rate limits hoặc hạn chế

4. **Khối lượng và định dạng dữ liệu**:
   - Dữ liệu quá lớn để xử lý hiệu quả
   - Định dạng không tương thích giữa các hệ thống

### 7.2. Giải pháp và best practices

1. **Thiết lập quy ước rõ ràng**:

   - Quy định cách đặt tên branch và commit message
   - Yêu cầu cập nhật Jira trước khi commit
   - Sử dụng tham chiếu chéo giữa các hệ thống

2. **Xây dựng pipeline ETL**:

   - Extract: Lấy dữ liệu từ các nguồn
   - Transform: Chuẩn hóa, làm sạch và kết hợp
   - Load: Đưa vào kho dữ liệu thống nhất

3. **Công cụ tích hợp**:

   - Sử dụng các giải pháp như Jira Git integration
   - Confluence-Jira macros để liên kết tài liệu
   - Công cụ BI như Power BI, Tableau để kết nối nhiều nguồn

4. **Tự động hóa**:
   - Scripts định kỳ trích xuất và kết hợp dữ liệu
   - Cảnh báo khi phát hiện dữ liệu không đồng bộ
   - Dashboard tự động cập nhật

## 8. Chuẩn bị dữ liệu kết hợp cho phân tích AI

Sau khi kết hợp dữ liệu từ các nguồn, cần chuẩn bị dữ liệu phù hợp cho AI:

1. **Xác định mục tiêu phân tích**:

   - Dự báo thời gian hoàn thành
   - Phát hiện rủi ro tiềm ẩn
   - Phân tích nguyên nhân gốc rễ của vấn đề

2. **Tạo dataset phù hợp**:

   - Xác định các features quan trọng từ mỗi nguồn dữ liệu
   - Tạo format data phù hợp (CSV, JSON) với context đầy đủ
   - Loại bỏ outliers và dữ liệu nhiễu

3. **Bổ sung thông tin context**:
   - Metadata về dự án và team
   - Thông tin về quy trình đang áp dụng
   - Các yếu tố bên ngoài ảnh hưởng (ví dụ: ngày lễ, sự kiện đặc biệt)

> 🔗 **Kết nối**: Nội dung này sẽ được đề cập chi tiết hơn trong phần "Chuẩn bị dữ liệu để đưa cho AI"

## Bài tập thực hành

1. Từ một project mẫu có dữ liệu Jira và Git, hãy tạo một script Python đơn giản để kết hợp:

   - Danh sách issues từ một sprint cụ thể
   - Lịch sử commit liên quan đến các issues đó
   - Xuất ra file CSV thể hiện mối quan hệ

2. Tạo một dashboard đơn giản (có thể dùng Excel) thể hiện:

   - Tiến độ sprint (từ Jira)
   - Activity heatmap (từ Git)
   - Phân bố công việc giữa các thành viên

3. Từ dữ liệu mẫu về một User Story, kết hợp:
   - Mô tả yêu cầu từ Confluence
   - Thông tin triển khai từ Jira
   - Các commits liên quan từ Git
     Và chuẩn bị prompt để AI phân tích tiến độ thực hiện so với yêu cầu.

## Tài liệu tham khảo

- [Jira & GitHub Integration Guide](https://support.atlassian.com/jira-cloud-administration/docs/integrate-with-github/)
- [Confluence REST API Documentation](https://developer.atlassian.com/cloud/confluence/rest/v1/intro/)
- [Google Drive API Overview](https://developers.google.com/drive/api/guides/about-sdk)
- [Data Integration Best Practices](https://www.talend.com/resources/data-integration-best-practices/)
- [ETL vs ELT: Differences and Use Cases](https://www.xplenty.com/blog/etl-vs-elt/)
