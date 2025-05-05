## 1. Đặc thù dự án phát triển phần mềm

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Nhận diện được các đặc điểm đặc thù của dự án phần mềm.
- Hiểu vì sao việc quản lý dự án phần mềm đòi hỏi những phương pháp linh hoạt và phù hợp.
- Nhận thức được vai trò quan trọng của giao tiếp, thay đổi và chất lượng trong phát triển phần mềm.

---

### 🧩 Nội dung chi tiết

#### 1.1. Phần mềm là sản phẩm đặc biệt

- Không có hình thái vật lý, mang tính **trừu tượng và logic**.
- Được phát triển dựa trên **yêu cầu thay đổi liên tục** của người dùng.
- Khó định lượng và đo lường chính xác **tiến độ, chất lượng và độ hoàn thiện**.

#### 1.2. Đặc điểm chính của dự án phát triển phần mềm

##### 🌀 Thay đổi yêu cầu là điều tất yếu

- Khách hàng thường **không xác định rõ ngay từ đầu** họ muốn gì.
- Càng gần giai đoạn hoàn thành, **yêu cầu càng rõ ràng hơn** → sinh ra thay đổi.
- Môi trường kinh doanh thay đổi cũng kéo theo thay đổi trong yêu cầu.

**🎯 Case Study:**

> Dự án xây dựng hệ thống bán vé trực tuyến cho rạp chiếu phim. Ban đầu khách hàng chỉ yêu cầu “chọn phim – đặt vé – thanh toán”. Sau vài sprint đầu, họ muốn thêm:
>
> - Đặt chỗ theo sơ đồ ghế.
> - Tích hợp thanh toán qua ví điện tử.
> - Chương trình tích điểm cho thành viên.
>
> Nếu đội dự án theo mô hình cứng nhắc (Waterfall), sẽ rất khó thích ứng với thay đổi này.

---

##### 🧠 Tính sáng tạo và tri thức cao

- Phần mềm là sản phẩm trí tuệ, phụ thuộc vào khả năng giải quyết vấn đề và hiểu biết của người phát triển.
- Không thể kiểm soát giống như dây chuyền sản xuất vật lý.

**🎯 Case Study:**

> Một startup phát triển ứng dụng học tiếng Anh tích hợp AI. Không có đặc tả rõ ràng, nhóm phát triển phải vừa làm vừa thử nghiệm các giải pháp:
>
> - Giao diện chatbot hay flashcard?
> - Gợi ý từ bằng AI thế nào để dễ học?
>
> Sự thành công phụ thuộc nhiều vào sự sáng tạo và phản hồi của người dùng cuối.

---

##### 🔁 Tính lặp lại và tiến hóa

- Không thể “làm xong là hết”.
- Phần mềm cần **duy trì, cập nhật, nâng cấp thường xuyên** sau khi bàn giao.

**🎯 Case Study:**

> Một công ty phát triển phần mềm quản lý kho cho chuỗi siêu thị. Sau khi triển khai 1 năm:
>
> - Phải bổ sung hỗ trợ xuất hóa đơn điện tử.
> - Thay đổi theo quy định thuế mới.
> - Nâng cấp hiệu năng khi hệ thống có thêm 100+ cửa hàng.
>
> Điều này yêu cầu phần mềm phải có khả năng bảo trì lâu dài.

---

##### 🤝 Giao tiếp là yếu tố then chốt

- Hầu hết vấn đề trong dự án phần mềm đến từ **truyền thông sai lệch**.
- Giao tiếp hiệu quả giữa **developer – khách hàng – quản lý dự án – tester** là yếu tố sống còn.

**🎯 Case Study:**

> Trong một dự án gia công phần mềm nước ngoài, nhóm dev hiểu sai khái niệm “Invoice Due Date” thành “Ngày tạo hóa đơn” thay vì “Hạn thanh toán”.
> → Tạo ra lỗi nghiêm trọng và ảnh hưởng đến nghiệp vụ kế toán của khách hàng.

---

##### 🔗 Phụ thuộc và tích hợp phức tạp

- Phần mềm thường không hoạt động đơn lẻ → cần tích hợp với hệ thống khác.
- Cần xử lý **phụ thuộc hệ thống, dữ liệu, API, môi trường chạy**, v.v.

**🎯 Case Study:**

> Hệ thống CRM của một doanh nghiệp cần kết nối với API của nhà mạng để gửi tin nhắn chăm sóc khách hàng.
> Tuy nhiên:
>
> - API bị thay đổi định kỳ mà không báo trước.
> - Hệ thống khách hàng dùng phiên bản PHP cũ không tương thích JSON schema mới.
>
> Nhóm phát triển phải luôn theo dõi, phản ứng nhanh và kiểm soát rủi ro tích hợp.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Bạn từng tham gia dự án nào mà yêu cầu thay đổi nhiều lần chưa? Điều gì gây ra sự thay đổi đó?
- Bạn nghĩ điều gì là khó nhất khi làm việc trong một nhóm phát triển phần mềm?
- Làm sao để giảm thiểu rủi ro từ việc giao tiếp sai lệch giữa các vai trò?

---

### 📌 Tài liệu & Tham khảo

- “Software Engineering” – Ian Sommerville, chương 1 & 2.
- “The Mythical Man-Month” – Frederick P. Brooks
- https://www.ibm.com/blogs/industries/why-software-projects-fail/
