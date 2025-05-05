## 2. Vòng đời phát triển phần mềm (SDLC)

### 🎯 Mục tiêu phần học

Sau khi học xong phần này, học viên sẽ:

- Hiểu được khái niệm vòng đời phát triển phần mềm (Software Development Life Cycle - SDLC).
- Nắm rõ các giai đoạn chính trong SDLC.
- Nhận biết ưu nhược điểm và tình huống áp dụng của các mô hình phát triển phần mềm phổ biến như Waterfall, V-Model, Iterative và Agile.

---

### 🧩 Nội dung chi tiết

#### 2.1. Khái niệm SDLC là gì?

**SDLC** là viết tắt của _Software Development Life Cycle_, nghĩa là **vòng đời phát triển phần mềm**.  
Hiểu đơn giản, đây là một chu trình có hệ thống gồm nhiều bước giúp nhóm phát triển tạo ra phần mềm đạt chất lượng, đúng yêu cầu, đúng thời hạn và ngân sách.

---

#### 2.2. Các giai đoạn chính trong SDLC

1. **Phân tích yêu cầu (Requirement Analysis)**

   - Tìm hiểu và làm rõ nhu cầu thực tế của người dùng.
   - Tạo tài liệu mô tả yêu cầu phần mềm (gọi là SRS – Software Requirements Specification).

2. **Thiết kế hệ thống (System Design)**

   - Lên kế hoạch cho cấu trúc phần mềm, cơ sở dữ liệu và giao diện người dùng.
   - Xác định công nghệ và kiến trúc phần mềm sẽ sử dụng.

3. **Lập trình (Implementation / Coding)**

   - Lập trình phần mềm dựa trên bản thiết kế đã có.
   - Chia nhỏ công việc theo từng chức năng hoặc phần của hệ thống.

4. **Kiểm thử (Testing)**

   - Kiểm tra phần mềm để đảm bảo hoạt động đúng như yêu cầu.
   - Các loại kiểm thử:
     - **Kiểm thử đơn vị (Unit Test):** Kiểm tra từng phần nhỏ của chương trình.
     - **Kiểm thử tích hợp (Integration Test):** Kiểm tra các phần sau khi ghép lại với nhau.
     - **Kiểm thử hệ thống (System Test):** Kiểm tra toàn bộ hệ thống.
     - **Kiểm thử chấp nhận (Acceptance Test):** Kiểm tra với người dùng để xác nhận phần mềm đáp ứng nhu cầu.

5. **Triển khai (Deployment)**

   - Cài đặt phần mềm vào môi trường sử dụng thực tế (máy chủ, điện thoại, máy tính của người dùng...).

6. **Bảo trì (Maintenance)**
   - Sửa lỗi phát sinh, cập nhật chức năng mới, hoặc nâng cấp cho phù hợp với môi trường thay đổi.

---

### 📊 Các mô hình phát triển phần mềm phổ biến

#### 🔹 Mô hình thác nước (Waterfall Model)

- Các bước thực hiện theo thứ tự **từ trên xuống dưới**, không quay lại bước trước.
- Phù hợp với: Dự án nhỏ, yêu cầu rõ ràng, ít thay đổi trong quá trình làm.

**Ưu điểm:** Dễ quản lý tiến độ và chi phí.  
**Nhược điểm:** Khó thích nghi khi yêu cầu thay đổi.

**🎯 Case Study:**

> Dự án xây dựng phần mềm quản lý thư viện cho trường học. Vì yêu cầu đã được xác định sẵn từ Sở Giáo dục và không thay đổi nhiều, nhóm dùng mô hình Waterfall để làm theo từng bước, đảm bảo đúng tiến độ.

---

#### 🔹 Mô hình chữ V (V-Model)

- Là phiên bản nâng cao của Waterfall, nhấn mạnh sự **kiểm thử song song với từng bước phát triển**.
- Ví dụ: Sau khi viết yêu cầu thì lên kế hoạch kiểm thử chấp nhận; sau khi thiết kế thì lên kế hoạch kiểm thử hệ thống.

**Ưu điểm:** Đảm bảo phần mềm được kiểm tra chặt chẽ.  
**Nhược điểm:** Yêu cầu tài liệu kiểm thử rõ ràng từ sớm.

---

#### 🔹 Mô hình lặp (Iterative Model)

- Phát triển phần mềm **từng phần nhỏ theo chu kỳ**, mỗi lần sẽ bổ sung thêm chức năng.
- Người dùng có thể sử dụng bản thử sớm và góp ý liên tục.

**Ưu điểm:** Giảm rủi ro, dễ điều chỉnh khi có thay đổi.  
**Nhược điểm:** Dễ bị trễ nếu không kiểm soát tốt phạm vi công việc.

---

#### 🔹 Mô hình linh hoạt (Agile Model)

- **Agile** là phương pháp phát triển phần mềm linh hoạt, chia công việc thành các vòng lặp ngắn gọi là **"sprint"**.
- Một **sprint** thường kéo dài 1–4 tuần, sau mỗi sprint sẽ có một phần phần mềm hoàn chỉnh để người dùng sử dụng hoặc đánh giá.

**MVP (Minimum Viable Product)**: Là phiên bản đơn giản nhất của phần mềm, chỉ có những tính năng **cốt lõi và cần thiết nhất** để bắt đầu sử dụng hoặc thu hút người dùng.  
**UI/UX**: Là viết tắt của _User Interface_ (giao diện người dùng) và _User Experience_ (trải nghiệm người dùng), tức là phần giao diện và cảm nhận của người dùng khi sử dụng phần mềm.

**Ưu điểm:** Phản hồi nhanh, giảm rủi ro, người dùng tham gia thường xuyên.  
**Nhược điểm:** Cần sự phối hợp chặt chẽ từ nhóm phát triển và người dùng.

**🎯 Case Study:**

> Một nhóm startup muốn phát triển ứng dụng giao đồ ăn.  
> Họ dùng phương pháp Agile để chia thành nhiều vòng sprint:
>
> - Sprint 1: Làm MVP chỉ gồm đặt món và thanh toán.
> - Sprint 2: Cải tiến UI/UX theo góp ý của người dùng.
> - Sprint 3: Bổ sung theo dõi đơn hàng theo thời gian thực.
>   Nhờ cách làm này, họ đưa sản phẩm ra thị trường sau chỉ 2 tháng.

---

### 🧠 Câu hỏi thảo luận gợi mở

- Nếu bạn làm dự án cho cơ quan nhà nước với yêu cầu rõ ràng, bạn nên chọn mô hình nào? Vì sao?
- Bạn từng dùng phần mềm nào khiến bạn cảm thấy UI/UX tốt hay tệ? Hãy chia sẻ lý do.
- Theo bạn, điểm khác nhau rõ nhất giữa Waterfall và Agile là gì?

---

### 📌 Tài liệu & Tham khảo

- Sách “Software Engineering” – Ian Sommerville, chương 2 & 3.
- Agile Manifesto: https://agilemanifesto.org
- https://www.tutorialspoint.com/sdlc/index.htm
