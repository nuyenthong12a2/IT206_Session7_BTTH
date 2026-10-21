# Từ Backlog cũ đến Backlog chuẩn: Module “Đánh giá sản phẩm” (GreenCart)

*Bài tập tổng hợp: Phần A (chẩn đoán) và Phần B (Backlog hoàn thiện)*

## PHẦN A: CHẨN ĐOÁN BACKLOG HIỆN TRẠNG

### A1. S1: ĐÚNG

> “Là một khách hàng, tôi muốn chấm sao (1–5 sao) cho sản phẩm đã mua, để tôi chia sẻ mức độ hài lòng của mình.”

| Tiêu chí | Nhận xét |
| --- | --- |
| Cấu trúc | Đủ vai trò (khách hàng), mong muốn (chấm sao), giá trị (chia sẻ mức hài lòng) |
| Independent | Làm được riêng, không cần chờ bình luận hay ảnh |
| Negotiable | Chưa áp đặt giao diện (sao vàng, slider…) |
| Valuable | Có giá trị rõ cho khách và cho shop |
| Estimable | Phạm vi rõ: một thao tác chọn 1–5 sao |
| Small | Hoàn thành trong một Sprint |
| Testable | Kiểm tra được: chọn 1–5 thì lưu đúng, ngoài khoảng đó thì không hợp lệ |

### A2. S2: SAI

> “Cho phép khách chấm sao, viết bình luận, đính kèm ảnh, gửi đánh giá, hệ thống kiểm duyệt nội dung, rồi hiển thị công khai lên trang sản phẩm.”

**Vi phạm nguyên tắc phân cấp Epic/Feature/User Story.** S2 mô tả cả một luồng nghiệp vụ end-to-end gồm 6 chức năng, nên thực chất là cấp **Feature** bị điền nhầm vào ô User Story. Ngoài ra, “chấm sao” đã trùng với S1.

**Vi phạm cấu trúc.** Câu không theo dạng *As a… I want… so that…*: thiếu vai trò người dùng, thiếu giá trị mang lại, viết theo kiểu liệt kê chức năng hệ thống.

**Vi phạm INVEST:**

| Tiêu chí | Vi phạm ở đâu |
| --- | --- |
| **S**mall | Gộp 6 việc, không thể xong trong một Sprint |
| **E**stimable | Nhiều ẩn số (quy tắc kiểm duyệt, dung lượng ảnh…), team không ước lượng được |
| **I**ndependent | Trộn nhiều actor (khách, hệ thống, người kiểm duyệt) và nhiều phần việc phụ thuộc nhau |
| **V**aluable | Không nêu giá trị cho người dùng nào |
| **T**estable | Không có tiêu chí chấp nhận chung, “xong” nghĩa là gì thì không rõ |
| **N**egotiable | Ghi sẵn từng bước giải pháp, không còn chỗ thương lượng |

### A3. Vì sao S2 không thể đưa thẳng vào Sprint

1. Quá lớn nên không có Definition of Done chung và không hoàn thành trọn vẹn trong một Sprint.
2. Không ước lượng được Story Point.
3. Không ưu tiên được từng phần, ví dụ “chấm sao” làm trước còn “đính kèm ảnh” để sau.
4. Có phụ thuộc chéo: kiểm duyệt cần có đánh giá, hiển thị cần có kiểm duyệt.
5. Không phân công và demo được từng phần, nên Sprint Review khó kết luận Done hay chưa.

## PHẦN B: BACKLOG ĐÃ HOÀN THIỆN

**EPIC: Đánh giá & Nhận xét sản phẩm**

### F1: Viết đánh giá sản phẩm

| ID | User Story |
| --- | --- |
| **S1** (giữ nguyên) | Là một khách hàng, tôi muốn chấm sao (1–5 sao) cho sản phẩm đã mua, để tôi chia sẻ mức độ hài lòng của mình. |
| **S2.1** (tách từ S2) | Là một khách hàng, tôi muốn viết bình luận văn bản kèm đánh giá sao, để tôi giải thích lý do hài lòng hoặc không hài lòng cho người khác tham khảo. |
| **S2.2** (tách từ S2) | Là một khách hàng, tôi muốn đính kèm ảnh thực tế của sản phẩm vào đánh giá, để người mua sau thấy được chất lượng sản phẩm thật. |
| **S2.3** (tách từ S2) | Là một người kiểm duyệt nội dung, tôi muốn duyệt hoặc từ chối đánh giá mới trước khi công khai, để nội dung spam hoặc xúc phạm không xuất hiện trên trang sản phẩm. |
| **S3** (bổ sung) | Là một khách hàng, tôi muốn gửi đánh giá của mình và nhận thông báo xác nhận đã gửi (đang chờ duyệt), để tôi biết đánh giá đã được ghi nhận. |

**Tiêu chí chấp nhận gợi ý**

- **S2.1:** Bình luận tối đa 1.000 ký tự; có thể để trống khi đã chấm sao.
- **S2.2:** Tối đa 3 ảnh, định dạng JPG/PNG, mỗi ảnh ≤ 5 MB.
- **S2.3:** Đánh giá ở trạng thái “Chờ duyệt”; người kiểm duyệt chọn Duyệt hoặc Từ chối (kèm lý do). Chỉ đánh giá “Đã duyệt” mới được công khai.
- **S3:** Chỉ khách đã nhận hàng mới gửi được. Sau khi gửi hiện thông báo “Đánh giá đang chờ duyệt”.

### F2: Xem đánh giá sản phẩm

*Tên Feature đề xuất cho F2 (trước đây để trống). Phần “hiển thị công khai” của S2 cũ được chuyển về đây vì đây là hành vi của người đọc, không phải người viết.*

| ID | User Story |
| --- | --- |
| **S4** | Là một khách hàng đang xem sản phẩm, tôi muốn thấy điểm đánh giá trung bình và tổng số lượt đánh giá, để tôi nhanh chóng nắm được mức độ hài lòng chung trước khi quyết định mua. |
| **S5** | Là một khách hàng đang xem sản phẩm, tôi muốn đọc danh sách bình luận và ảnh đã được duyệt của những người mua trước, để tôi hiểu trải nghiệm thực tế và tự tin hơn khi mua. |
| **S6** (tùy chọn) | Là một khách hàng đang xem sản phẩm, tôi muốn lọc đánh giá theo số sao, để tôi tập trung đọc các nhận xét tích cực hoặc tiêu cực mà mình quan tâm. |

**Tiêu chí chấp nhận gợi ý**

- **S4:** Điểm trung bình làm tròn 1 chữ số thập phân; chỉ tính các đánh giá đã duyệt.
- **S5:** Chỉ hiển thị đánh giá đã duyệt, sắp xếp mới nhất trước, phân trang 10 đánh giá mỗi trang.
- **S6:** Chọn 1–5 sao thì danh sách chỉ còn các đánh giá tương ứng.

### Kiểm tra INVEST nhanh

| Story | I | N | V | E | S | T |
| --- | --- | --- | --- | --- | --- | --- |
| S1 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| S2.1 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| S2.2 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| S2.3 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| S3 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| S4 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| S5 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| S6 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |

Các Story vẫn có phụ thuộc nhẹ về thứ tự (ví dụ S5 cần dữ liệu từ S2.3), nhưng mỗi Story đều có thể phát triển, kiểm thử và demo riêng, nên vẫn đạt Independent ở mức chấp nhận được.

### Gợi ý thứ tự ưu tiên cho Product Owner

**S1 → S3 → S2.1 → S2.3 → S4 → S5**, sau đó S2.2 và S6. Đây là luồng tối thiểu để có một đánh giá được viết, duyệt và hiển thị.

## Ý chính để trình bày 2 phút

1. S2 sai vì là Feature đội lốt Story: quá lớn, thiếu vai trò và giá trị, không ước lượng hay kiểm thử được.
2. Cách sửa: tách theo giá trị người dùng (bình luận, ảnh, kiểm duyệt, gửi) và chuyển phần “hiển thị” sang Feature F2.
3. Mỗi Story mới có vai trò, mong muốn, giá trị và tiêu chí chấp nhận riêng, nên đủ điều kiện vào Sprint.
