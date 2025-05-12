# Hiểu dữ liệu từ Git log

## 1. Tổng quan về Git log và giá trị của dữ liệu

Git log là công cụ mạnh mẽ trong hệ thống quản lý phiên bản Git, cho phép chúng ta xem lịch sử commit của repository. Thông tin này không chỉ đơn thuần là "ai đã thay đổi gì và khi nào" mà còn cung cấp nhiều insights quý giá về:

- **Tiến độ phát triển**: Nhịp độ và tần suất phát triển của dự án
- **Phân bố công việc**: Các thành viên đóng góp vào những phần nào của code
- **Điểm nóng (hotspots)**: Files/modules nào thay đổi nhiều nhất
- **Chất lượng code**: Thông qua message commit và tần suất sửa lỗi
- **Giai đoạn dự án**: Các mốc phát triển quan trọng

## 2. Thông tin quan trọng có thể trích xuất từ Git log

Mỗi commit trong Git log chứa nhiều thông tin có giá trị:

- **Commit hash**: Mã định danh duy nhất cho mỗi commit
- **Author**: Người thực hiện thay đổi
- **Date**: Thời gian commit
- **Commit message**: Mô tả về những thay đổi
- **Changed files**: Các file đã được thêm, sửa, xóa
- **Diff content**: Nội dung chi tiết đã thay đổi
- **Branch/tag information**: Thông tin về nhánh và tag
- **Merge details**: Thông tin về việc merge code

## 3. Các lệnh Git log cơ bản

### 3.1. `git log`

Lệnh đơn giản nhất để xem lịch sử commit:

```bash
git log
```

Kết quả hiển thị đầy đủ thông tin về mỗi commit:

```
commit 3c4e9cd789df17d0b07e121416aa0e4da7613da9
Author: Jane Doe <jane.doe@example.com>
Date:   Wed Apr 3 19:01:55 2024 +0700

    Fix login error on mobile devices

commit 8d92f141a980173e3b2347810dfe29e97d2bca24
Author: John Smith <john.smith@example.com>
Date:   Tue Apr 2 14:32:10 2024 +0700

    Add user profile page
```

### 3.2. `git log --oneline`

Hiển thị mỗi commit trên một dòng, gọn gàng hơn:

```bash
git log --oneline
```

Kết quả:

```
3c4e9cd Fix login error on mobile devices
8d92f14 Add user profile page
f7d2a3c Update README with installation instructions
```

> 💡 **Mẹo**: Rất hữu ích khi cần xem nhanh lịch sử commit hoặc khi commit history dài.

### 3.3. `git log --stat`

Hiển thị thêm thống kê về các file đã thay đổi:

```bash
git log --stat
```

Kết quả:

```
commit 3c4e9cd789df17d0b07e121416aa0e4da7613da9
Author: Jane Doe <jane.doe@example.com>
Date:   Wed Apr 3 19:01:55 2024 +0700

    Fix login error on mobile devices

 src/components/Login.js | 15 +++++++++------
 src/styles/mobile.css   |  7 +++++++
 2 files changed, 16 insertions(+), 6 deletions(-)
```

> ✅ **Ứng dụng**: Giúp xác định các file thường xuyên thay đổi và mức độ thay đổi.

### 3.4. `git log --graph`

Hiển thị lịch sử commit dưới dạng đồ thị, đặc biệt hữu ích cho các nhánh:

```bash
git log --graph --oneline --all
```

Kết quả:

```
* 3c4e9cd (HEAD -> main) Fix login error on mobile devices
* 8d92f14 Add user profile page
| * f7d2a3c (feature-notifications) Implement push notifications
| * 5a1b2c3 Create notification service
|/
* d4e5f6a Initial commit
```

> 🎯 **Mục đích**: Hiểu rõ luồng phát triển và merge giữa các nhánh.

## 4. Lọc và định dạng dữ liệu Git log

### 4.1. Lọc theo thời gian

```bash
# Xem commit từ 2 tuần trước
git log --since="2 weeks ago"

# Xem commit từ ngày cụ thể
git log --since="2024-01-01" --until="2024-03-31"
```

### 4.2. Lọc theo tác giả

```bash
# Xem commit của một người cụ thể
git log --author="Jane Doe"

# Sử dụng biểu thức chính quy
git log --author="jane\|john"
```

### 4.3. Lọc theo nội dung

```bash
# Tìm commit có từ khóa trong message
git log --grep="bug fix"

# Tìm commit thay đổi một chuỗi cụ thể trong code
git log -S"function login()"
```

### 4.4. Lọc theo file

```bash
# Xem lịch sử một file cụ thể
git log -- src/components/Login.js

# Xem lịch sử nhiều file
git log -- src/components/Login.js src/styles/mobile.css
```

### 4.5. Định dạng đầu ra tùy chỉnh

Sử dụng `--pretty=format` để tùy chỉnh định dạng:

```bash
git log --pretty=format:"%h,%an,%ad,%s" --date=short
```

Kết quả:

```
3c4e9cd,Jane Doe,2024-04-03,Fix login error on mobile devices
8d92f14,John Smith,2024-04-02,Add user profile page
f7d2a3c,Alex Johnson,2024-04-01,Update README with installation instructions
```

Một số placeholder phổ biến:

- `%h`: commit hash (ngắn)
- `%H`: commit hash đầy đủ
- `%an`: tên tác giả
- `%ae`: email tác giả
- `%ad`: ngày commit
- `%s`: subject (tiêu đề commit)
- `%b`: body (nội dung commit)

## 5. Trích xuất dữ liệu Git log sang CSV/JSON

### 5.1. Export sang CSV

Sử dụng lệnh format và chuyển hướng vào file:

```bash
git log --pretty=format:"%h,%an,%ae,%ad,%s" --date=short > git_history.csv
```

Tạo header cho CSV file:

```bash
echo "CommitID,Author,Email,Date,Message" > git_history.csv
git log --pretty=format:"%h,%an,%ae,%ad,%s" --date=short >> git_history.csv
```

### 5.2. Export sang JSON

Tạo JSON với bash script đơn giản:

```bash
echo "[" > git_history.json
git log --pretty=format:'{"commit": "%h", "author": "%an", "email": "%ae", "date": "%ad", "message": "%s"},' --date=short | sed '$ s/,$//g' >> git_history.json
echo "]" >> git_history.json
```

### 5.3. Sử dụng công cụ hỗ trợ

Có nhiều công cụ giúp trích xuất dữ liệu Git dễ dàng hơn:

- **GitStats**: Tạo báo cáo thống kê từ repo Git
- **Gitinspector**: Phân tích thống kê cho repo Git
- **Git-extras**: Bổ sung nhiều lệnh hữu ích cho Git

## 6. Các chỉ số quan trọng từ Git log

### 6.1. Tần suất commit

- **Số lượng commit theo thời gian**: Đo lường hoạt động phát triển
- **Commit density**: Mật độ commit trong các giai đoạn dự án
- **Commit pattern**: Kiểu commit (đều đặn hay bùng nổ gần deadline)

### 6.2. Thời gian commit

- **Thời điểm trong ngày**: Xác định thời gian làm việc của team
- **Ngày trong tuần**: Pattern làm việc trong tuần
- **Sự phân bố theo múi giờ**: Hiểu về team phân tán địa lý

### 6.3. Phân bố công việc

- **Commit theo tác giả**: Mức độ đóng góp của từng thành viên
- **Expertise areas**: Ai thường làm việc với phần nào của code
- **Collaboration patterns**: Mô hình hợp tác giữa các thành viên

### 6.4. Phân tích nội dung commit

- **Commit size**: Kích thước trung bình của mỗi commit
- **Files changed**: Số lượng và loại files thường được thay đổi
- **Hotspots**: Các file/module thường xuyên được chỉnh sửa
- **Change patterns**: Mẫu thay đổi (thêm mới, sửa đổi, xóa)

## 7. Ví dụ thực tế: Trích xuất và phân tích dữ liệu từ một dự án

### Tình huống: Đánh giá hiệu suất team và tiến độ dự án

#### Yêu cầu:

- Xác định các giai đoạn phát triển chính
- Đánh giá mức độ đóng góp của các thành viên
- Phát hiện các "hotspot" trong code
- Hiểu mẫu làm việc của team (thời gian, tần suất)

#### Các bước thực hiện:

1. **Thu thập dữ liệu cơ bản**:

   ```bash
   git log --pretty=format:"%h,%an,%ad,%s" --date=iso > commits_history.csv
   ```

2. **Phân tích tần suất commit theo ngày**:

   ```bash
   git log --date=short --format='%ad' | sort | uniq -c
   ```

3. **Phân tích đóng góp của từng thành viên**:

   ```bash
   git shortlog -sn --all
   ```

4. **Tìm các file thay đổi nhiều nhất**:

   ```bash
   git log --name-only --pretty=format: | sort | uniq -c | sort -nr | head -10
   ```

5. **Xem thời điểm commit phổ biến**:
   ```bash
   git log --format='%ad' --date=format:'%H' | sort | uniq -c
   ```

#### Phân tích kết quả:

Từ dữ liệu thu thập được, chúng ta có thể:

- Vẽ biểu đồ hoạt động dự án theo thời gian
- Xác định thời điểm bùng nổ và suy giảm hoạt động
- Hiểu được các module phức tạp (thường xuyên thay đổi)
- Đánh giá sự cân bằng trong phân công công việc

## 8. Kết hợp dữ liệu Git với Jira

Khi commit messages chứa ID của Jira issues (ví dụ: PROJ-123), chúng ta có thể liên kết:

1. **Trích xuất commit với ID Jira**:

   ```bash
   git log --grep="PROJ-[0-9]" --pretty=format:"%h,%an,%ad,%s" > jira_related_commits.csv
   ```

2. **Phân tích thời gian giải quyết vấn đề**:
   Kết hợp dữ liệu Jira về thời gian tạo issue và dữ liệu Git về thời gian commit liên quan.

3. **Phân tích mối liên hệ giữa loại issue và số lượng commit**:
   Xem mỗi loại Jira issue (Bug, Story, Task) thường cần bao nhiêu commit để hoàn thành.

> 🔗 **Kết nối**: Phần này sẽ được đề cập chi tiết hơn trong phần "Kết hợp dữ liệu từ các nguồn".

## Bài tập thực hành

1. Từ một repository Git mẫu, sử dụng lệnh để trích xuất 10 commit gần nhất với thông tin author, date và message.

2. Tạo một file CSV chứa thông tin về commit theo từng tháng trong năm qua, bao gồm số lượng commit, số lượng file thay đổi và tên các tác giả.

3. Viết một script bash đơn giản để phân tích và hiển thị thông tin về:

   - Top 3 người đóng góp nhiều nhất
   - Top 5 file thay đổi nhiều nhất
   - Thời điểm trong ngày có nhiều commit nhất

4. Sử dụng Git log để tìm tất cả commit liên quan đến các issue có độ ưu tiên cao trong Jira (giả sử các commit có format "[HIGH] PROJ-XXX").

## Tài liệu tham khảo

- [Git Documentation - git-log](https://git-scm.com/docs/git-log)
- [Pro Git Book - Viewing the Commit History](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)
- [Git Log Cheat Sheet](https://devhints.io/git-log)
- [Git - Generating Statistics With gitstat](https://www.atlassian.com/git/tutorials/git-stats)
- [GitHub - Git Extras](https://github.com/tj/git-extras)
