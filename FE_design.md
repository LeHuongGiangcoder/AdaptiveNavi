# Frontend Design Document

**Ngôn ngữ:** Tiếng Việt
**Sản phẩm:** Thi thử và luyện tập adaptive cho học sinh 12

## 1. Nguyên tắc thiết kế chung (General Design Principles)

Dựa trên các tài liệu tham khảo và yêu cầu của bạn, giao diện người dùng sẽ tuân thủ các nguyên tắc sau:

*   **Sạch sẽ & Tập trung (Clean & Focused):** Bố cục tối giản, loại bỏ các yếu tố gây xao nhãng để học sinh tập trung tối đa vào nội dung câu hỏi và làm bài.
*   **Hiện đại (Modern):** Sử dụng các xu hướng thiết kế hiện đại để mang lại trải nghiệm mới mẻ và chuyên nghiệp.
*   **Bo tròn (Rounded Borders):** Các góc của các thành phần UI (buttons, cards, input fields) sẽ được bo tròn để tạo cảm giác mềm mại, thân thiện và hiện đại.
*   **Soft UI / Neumorphism (Gợi ý):** Áp dụng các hiệu ứng đổ bóng nhẹ nhàng, tinh tế để tạo chiều sâu và cảm giác "nổi" cho các thành phần, nhưng vẫn giữ được sự rõ ràng và dễ đọc.
*   **Màu sắc trang nhã (Elegant Colors):** Sử dụng bảng màu hài hòa, dễ chịu cho mắt, tránh các màu quá chói hoặc gây mỏi mắt khi sử dụng lâu dài.
*   **Phản hồi trực quan (Visual Feedback):** Cung cấp phản hồi rõ ràng cho các tương tác của người dùng (ví dụ: highlight khi chọn đáp án, hiệu ứng hover).

## 2. Typography

*   **Heading (Tiêu đề):** Font **Inter**
    *   Kích thước và trọng lượng (weight) sẽ được điều chỉnh linh hoạt cho H1, H2, H3, v.v., để đảm bảo phân cấp thông tin rõ ràng và dễ đọc.
*   **Text (Nội dung văn bản):** Font **Montserrat**
    *   Kích thước và trọng lượng sẽ được tối ưu cho nội dung chính, chú thích, metadata để đảm bảo dễ đọc trên mọi thiết bị.

## 3. Thiết kế Khu vực Câu hỏi (Question Section)

### 3.1. Hiển thị Câu hỏi chung

*   Mỗi câu hỏi sẽ được hiển thị trên một "card" hoặc một khu vực riêng biệt, có nền màu nhẹ nhàng và các góc bo tròn.
*   Số thứ tự câu hỏi sẽ được hiển thị rõ ràng (ví dụ: "Câu 1:", "Câu 2:").
*   Nội dung câu hỏi sẽ sử dụng font Montserrat, kích thước phù hợp để dễ đọc.

### 3.2. Xử lý Hình ảnh và Công thức Toán học

*   **Hình ảnh:**
    *   Hình ảnh sẽ được căn giữa hoặc căn trái tùy theo bố cục và kích thước.
    *   Kích thước hình ảnh sẽ được giới hạn để không làm vỡ bố cục hoặc chiếm quá nhiều không gian màn hình, có thể có chức năng zoom/phóng to khi click (tùy chọn).
    *   Các góc của hình ảnh có thể được bo tròn nhẹ để phù hợp với phong cách chung.
*   **Công thức Toán học:**
    *   Sử dụng thư viện hiển thị công thức toán học (ví dụ: MathJax hoặc KaTeX) để đảm bảo công thức được render đẹp, rõ ràng và chính xác.
    *   Font chữ và kích thước của công thức sẽ được tối ưu để dễ đọc, có thể lớn hơn một chút so với văn bản thông thường để nổi bật.
    *   Đảm bảo hiển thị tốt trên các thiết bị di động.

### 3.3. Hiển thị các dạng câu hỏi cụ thể

#### a. Câu hỏi trắc nghiệm (Multiple Choice A, B, C, D)

*   **Nội dung câu hỏi:** Hiển thị rõ ràng ở phía trên.
*   **Các lựa chọn (A, B, C, D):**
    *   Hiển thị theo **chiều ngang**, mỗi lựa chọn là một "button" hoặc "card" riêng biệt.
    *   Mỗi button/card sẽ có các góc bo tròn, nền màu nhẹ.
    *   Nội dung lựa chọn (A, B, C, D và văn bản/công thức đi kèm) sẽ được căn chỉnh hợp lý.
*   **Trạng thái được chọn:**
    *   Khi người dùng chọn một đáp án, button/card tương ứng sẽ được **highlight** rõ ràng (ví dụ: đổi màu nền, thêm viền, đổ bóng nhẹ) để phân biệt với các lựa chọn còn lại.
    *   Chỉ cho phép chọn một đáp án duy nhất.

#### b. Câu hỏi Đúng/Sai (True/False)

*   **Nội dung câu hỏi chính:** Hiển thị ở phía trên.
*   **Các ý nhỏ (ví dụ: 1a, 1b, 1c, 1d):**
    *   Sẽ được hiển thị dưới dạng danh sách hoặc bảng, mỗi ý trên một dòng riêng biệt.
    *   Mỗi ý sẽ bao gồm nội dung phát biểu và hai nút **"Đúng"** và **"Sai"** đặt cạnh nhau.
*   **Trạng thái được chọn:**
    *   Khi người dùng chọn "Đúng" hoặc "Sai" cho một ý, nút được chọn sẽ được **highlight** tương tự như câu trắc nghiệm.
    *   Đảm bảo người dùng có thể thay đổi lựa chọn của mình.

#### c. Câu hỏi trả lời ngắn (Short Answer)

*   **Nội dung câu hỏi:** Hiển thị rõ ràng ở phía trên.
*   **Ô nhập liệu (Input Field):**
    *   Một ô nhập liệu dạng text box sẽ được cung cấp để người dùng nhập câu trả lời.
    *   Kích thước của ô nhập liệu sẽ được thiết kế để phù hợp với bố cục tổng thể, đủ lớn để người dùng dễ dàng nhập và xem lại câu trả lời, nhưng không quá lớn gây mất cân đối.
    *   Góc của ô nhập liệu sẽ được bo tròn.
    *   Có thể có placeholder text (ví dụ: "Nhập câu trả lời của bạn...") để hướng dẫn người dùng.
    *   Không cần gợi ý định dạng câu trả lời trừ khi có yêu cầu cụ thể cho từng câu.

## 4. Thiết kế Khu vực Trả lời (Answering Section)

*   (Đã được tích hợp vào mục 3.3 cho từng dạng câu hỏi)

## 5. Thiết kế Khu vực Điều hướng Câu hỏi (Question Navigation Section)

*   **Vị trí:** Có thể đặt ở một thanh bên (sidebar) hoặc một thanh cố định ở phía dưới/trên màn hình.
*   **Hiển thị:**
    *   Một lưới các ô vuông/hình tròn nhỏ, mỗi ô tương ứng với một câu hỏi.
    *   Số thứ tự câu hỏi sẽ được hiển thị trong mỗi ô.
*   **Trạng thái:**
    *   **Chưa làm:** Màu nền mặc định (ví dụ: xám nhạt).
    *   **Đã làm:** Màu nền khác (ví dụ: xanh dương nhạt).
    *   **Đã đánh dấu (Flagged):** Có biểu tượng nhỏ (ví dụ: cờ, ngôi sao) trên ô để người dùng dễ dàng quay lại.
    *   **Câu hỏi hiện tại:** Ô sẽ được highlight rõ ràng (ví dụ: viền đậm, màu nền khác biệt).
*   **Chức năng:**
    *   Click vào ô bất kỳ để chuyển đến câu hỏi đó.
    *   Nút "Câu trước" và "Câu tiếp theo" để di chuyển tuần tự.

## 6. Đồng hồ đếm ngược và nút "Nộp bài"

*   **Đồng hồ đếm ngược:**
    *   Hiển thị rõ ràng, dễ nhìn, thường ở góc trên cùng của màn hình.
    *   Sử dụng font Inter hoặc Montserrat, kích thước đủ lớn để dễ theo dõi.
    *   Có thể đổi màu hoặc có hiệu ứng cảnh báo khi thời gian sắp hết.
*   **Nút "Nộp bài":**
    *   Nút chính, nổi bật, thường đặt ở cuối trang hoặc ở khu vực điều hướng.
    *   Sử dụng phong cách bo tròn, màu sắc nổi bật (ví dụ: màu chủ đạo của ứng dụng).
    *   Có thể có pop-up xác nhận trước khi nộp bài.

## 7. Màu sắc (Colors)

*   Sẽ được lựa chọn dựa trên các tài liệu tham khảo bạn cung cấp, ưu tiên các tông màu nhẹ nhàng, hiện đại và trang nhã.
*   Bảng màu sẽ bao gồm:
    *   Màu nền chính.
    *   Màu chữ.
    *   Màu highlight/chọn.
    *   Màu cho các trạng thái (đúng, sai, biết, hiểu, vận dụng).

Đây là bản nháp đầu tiên cho `FE_design.md`. Tôi sẽ tiếp tục cập nhật nó khi chúng ta có thêm các quyết định thiết kế khác.