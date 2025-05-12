# Cách Export dữ liệu từ Jira

## 1. Giới thiệu về export dữ liệu trong Jira

Jira không chỉ là công cụ theo dõi công việc, nó còn là kho dữ liệu quý giá về quá trình phát triển dự án. Việc export dữ liệu từ Jira cho phép chúng ta:

- Phân tích hiệu suất của team và dự án
- Chuẩn bị báo cáo cho stakeholders
- Lưu trữ thông tin lịch sử dự án
- Thu thập dữ liệu để AI phân tích và đưa ra insights

## 2. Các loại dữ liệu có thể xuất từ Jira

### 2.1. Issues (Vấn đề)

- **User Stories**: Các yêu cầu từ góc nhìn người dùng
- **Tasks**: Các công việc cần thực hiện
- **Bugs**: Lỗi cần được sửa
- **Epics**: Nhóm các user stories liên quan
- **Sub-tasks**: Công việc nhỏ hơn trong một task

### 2.2. Báo cáo Agile

- **Sprint Reports**: Kết quả của mỗi sprint
- **Velocity Charts**: Biểu đồ tốc độ làm việc của team
- **Burndown/Burnup Charts**: Tiến độ giải quyết công việc
- **Cumulative Flow Diagram**: Dòng chảy công việc qua các trạng thái

### 2.3. Thông tin thời gian và worklog

- **Time spent**: Thời gian đã dành cho mỗi issue
- **Time tracking**: Theo dõi thời gian ước tính và thực tế
- **Work logs**: Nhật ký công việc chi tiết

## 3. Các phương pháp export dữ liệu từ Jira

### 3.1. Export trực tiếp từ Board/Backlog

**Bước 1**: Truy cập vào Backlog hoặc Board của dự án  
**Bước 2**: Click vào biểu tượng "Export" (thường là hình bánh răng ⚙️ hoặc ba dấu chấm ⋮)  
**Bước 3**: Chọn định dạng xuất (CSV, Excel, etc.)  
**Bước 4**: Tải file xuống và lưu trữ

> 💡 **Mẹo**: Export từ Board cho phép bạn xuất các issues theo trạng thái hiện tại của chúng (To Do, In Progress, Done).

### 3.2. Sử dụng JQL (Jira Query Language) để lọc và export dữ liệu cụ thể

JQL là ngôn ngữ truy vấn mạnh mẽ của Jira, cho phép lọc issues theo nhiều tiêu chí khác nhau:

**Bước 1**: Truy cập vào "Issues" hoặc "Search for issues"  
**Bước 2**: Click "Advanced" để sử dụng JQL  
**Bước 3**: Nhập truy vấn JQL, ví dụ:

```
project = "Project X" AND status = "Done" AND sprint in openSprints()
```

**Bước 4**: Click "Search"  
**Bước 5**: Sau khi có kết quả, click "Export" và chọn định dạng

#### Một số ví dụ JQL hữu ích:

- Tất cả issues đã hoàn thành trong sprint hiện tại:  
  `project = "Project X" AND sprint in openSprints() AND status = "Done"`

- Bugs chưa được giải quyết có độ ưu tiên cao:  
  `project = "Project X" AND issuetype = Bug AND priority in (High, Highest) AND status != Done`

- Công việc đã được giao cho member cụ thể:  
  `project = "Project X" AND assignee = "username@company.com"`

- Issues đã được cập nhật trong tuần qua:  
  `project = "Project X" AND updated >= -7d`

### 3.3. Export từ báo cáo Agile

**Bước 1**: Truy cập vào "Reports" trong project  
**Bước 2**: Chọn loại báo cáo (Sprint Report, Velocity Chart, etc.)  
**Bước 3**: Xem báo cáo và tùy chỉnh thông số (nếu cần)  
**Bước 4**: Tìm tùy chọn export (thường là CSV hoặc Excel)  
**Bước 5**: Tải file xuống

## 4. Các định dạng xuất phổ biến và ứng dụng

### 4.1. CSV (Comma-Separated Values)

- **Ưu điểm**: Dễ dàng import vào Excel, Google Sheets, hoặc các công cụ phân tích dữ liệu
- **Nhược điểm**: Không giữ được định dạng phức tạp
- **Phù hợp cho**: Phân tích dữ liệu thô, import vào công cụ BI

### 4.2. Excel

- **Ưu điểm**: Giữ được nhiều định dạng hơn, dễ làm việc với các bảng tính
- **Nhược điểm**: Có thể gặp vấn đề về compatibility giữa các phiên bản
- **Phù hợp cho**: Báo cáo, phân tích nhanh, tạo biểu đồ

### 4.3. PDF

- **Ưu điểm**: Giữ nguyên định dạng, dễ chia sẻ
- **Nhược điểm**: Khó chỉnh sửa hoặc trích xuất dữ liệu
- **Phù hợp cho**: Báo cáo chính thức, chia sẻ với stakeholders

### 4.4. XML

- **Ưu điểm**: Cấu trúc dữ liệu đầy đủ, dễ parse bằng code
- **Nhược điểm**: Khó đọc trực tiếp, cần công cụ để xử lý
- **Phù hợp cho**: Tích hợp với các hệ thống khác, lưu trữ dữ liệu có cấu trúc

## 5. Thực hành export dữ liệu từ một project Jira mẫu

### Tình huống thực tế: Export dữ liệu cho báo cáo sprint review

#### Yêu cầu:

- Cần danh sách tất cả User Stories và Bugs đã hoàn thành trong sprint vừa qua
- Cần thông tin về thời gian ước tính và thời gian thực tế đã dành cho mỗi issue
- Cần biết ai đã giải quyết issue nào

#### Các bước thực hiện:

1. Truy cập vào dự án mẫu "ProjectX"
2. Vào mục "Issues" và sử dụng JQL:
   ```
   project = "ProjectX" AND sprint = "Sprint 5" AND status = Done AND issuetype in (Story, Bug)
   ```
3. Click "Export" và chọn Excel
4. Tùy chỉnh các trường cần xuất:
   - Summary (Tóm tắt issue)
   - Issue Type (Loại issue: Story/Bug)
   - Status (Trạng thái)
   - Assignee (Người được giao)
   - Reporter (Người báo cáo)
   - Created (Thời gian tạo)
   - Updated (Thời gian cập nhật)
   - Resolved (Thời gian giải quyết)
   - Original Estimate (Ước tính ban đầu)
   - Time Spent (Thời gian đã dùng)
5. Export và lưu file với tên "Sprint5_Completed_Issues.xlsx"

## 6. Hạn chế quyền truy cập và các lưu ý khi export dữ liệu

### 6.1. Vấn đề về quyền hạn

- Không phải tất cả người dùng đều có quyền export dữ liệu
- Admin hoặc Project Lead thường có quyền đầy đủ để export
- Một số loại báo cáo có thể chỉ khả dụng với người dùng cụ thể

### 6.2. Xử lý thông tin nhạy cảm

- Cân nhắc loại bỏ thông tin cá nhân khi chia sẻ dữ liệu
- Thận trọng với các comment có thể chứa thông tin nhạy cảm
- Không chia sẻ file export công khai mà không kiểm tra nội dung

### 6.3. Dữ liệu lớn và giới hạn export

- Jira thường có giới hạn số lượng issues có thể export trong một lần
- Nếu project lớn, cân nhắc chia nhỏ việc export theo sprint hoặc thời gian
- Export quá nhiều dữ liệu có thể làm chậm hệ thống

### 6.4. Lưu trữ và quản lý dữ liệu đã export

- Lập kế hoạch lưu trữ dữ liệu đã export (Google Drive, SharePoint, etc.)
- Đặt tên file có hệ thống (ví dụ: ProjectName_SprintX_Date_DataType.xlsx)
- Cập nhật dữ liệu định kỳ để đảm bảo thông tin luôn mới nhất
- Giữ lịch sử các bản export để theo dõi xu hướng theo thời gian

## 7. Chuẩn bị dữ liệu sau khi export cho phân tích AI

Sau khi export dữ liệu từ Jira, cần một số bước xử lý trước khi đưa cho AI:

1. **Kiểm tra tính đầy đủ**: Đảm bảo dữ liệu chứa đủ thông tin cần thiết
2. **Làm sạch dữ liệu**: Xử lý các trường trống, sửa lỗi format
3. **Định dạng lại**: Chuyển đổi thành format phù hợp (CSV, JSON) cho AI
4. **Thêm context**: Bổ sung thông tin về dự án, mục tiêu phân tích
5. **Xóa thông tin nhạy cảm**: Ẩn danh hóa dữ liệu nếu cần thiết

> 🔗 **Kết nối**: Nội dung này sẽ được đề cập chi tiết hơn trong phần 4 "Chuẩn bị dữ liệu để đưa cho AI"

## Bài tập thực hành

1. Sử dụng tài khoản Jira demo được cung cấp, export danh sách tất cả bugs đã được giải quyết trong sprint gần nhất.

2. Viết một truy vấn JQL để tìm tất cả user stories chưa được ước tính story points và export kết quả ra file CSV.

3. Từ dữ liệu đã export, hãy tạo một bảng tính Excel đơn giản phân tích:
   - Số lượng issues theo loại (Story, Bug, Task)
   - Thời gian trung bình để giải quyết mỗi loại issue
   - Phân bố công việc giữa các thành viên team

## Tài liệu tham khảo

- [Jira Knowledge Base: Advanced Searching](https://support.atlassian.com/jira-software-cloud/docs/advanced-search-reference-jql-fields/)
- [Atlassian Community: JQL Cheat Sheet](https://community.atlassian.com/t5/Jira-articles/JQL-Cheat-Sheet/ba-p/495955)
- [Tài liệu Export Issues từ Jira](https://support.atlassian.com/jira-cloud-administration/docs/import-and-export-issues/)
- [Hướng dẫn Jira Reporting](https://www.atlassian.com/software/jira/guides/reporting/overview)
