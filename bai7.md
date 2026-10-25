# Phần 1: Phân tích lỗi
1. Phân tích lỗi từng dòng tiêu đề & Cơ chế hoạt động của Auto TOC
Nguyên nhân Auto TOC không hoạt động:
Auto TOC (Table of Contents) trong Microsoft Word hoạt động dựa trên cơ chế quét thẻ Style (nhãn phân cấp) được gán cho các đoạn văn bản. Word chỉ thu thập những đoạn văn được gán chính thức các nhãn Heading 1, Heading 2, Heading 3,... vào mục lục.
Định dạng thủ công (Manual Formatting): Chỉ là các thao tác trực quan (thay đổi font chữ, cỡ chữ, màu sắc, tô vàng, in đậm) trên nền đoạn văn bản mang nhãn Normal. Word coi các dòng này là văn bản nội dung thông thường, hoàn toàn không có thuộc tính phân cấp (Outline Level).
Vì cả 7 dòng tiêu đề trong bài đều mang nhãn Normal và chỉ được chỉnh sửa trực quan thủ công, bộ quét References → Table of Contents không tìm thấy bất kỳ thẻ Heading nào, dẫn đến kết quả Mục lục xuất ra bị rỗng.
Dòng tiêu đềĐịnh dạng hiện tạiLỗi cấu trúc & lý do Auto TOC bỏ quaCấp Style đúng1. Thông tin chung hội nghịChữ thường, cỡ 16, In đậm, Tô vàngMang nhãn Normal + định dạng thủ công. Word không nhận diện đây là tiêu đề lớn.
- Heading 1.1. Tên hội nghịNormal + in đậm + cỡ 14Mang nhãn Normal + định dạng thủ công.
- Heading 1.2. Thời gian & địa điểmNormal + in đậm + cỡ 14Mang nhãn Normal + định dạng thủ công
- Heading 2. Cơ cấu ban tổ chứcChữ thường, cỡ 16, In đậm, Tô vàngMang nhãn Normal + định dạng thủ công.
- Heading 2.1. Ban Nội dungNormal + cỡ 13 + màu xanhMang nhãn Normal + định dạng thủ công.
- Heading 2.1.1. Tiểu ban Kỹ thuậtNormal + cỡ 13 + màu xanhBị nhầm sang Heading 3 về mặt trực quan, bản chất vẫn là Normal thủ công và sai phân cấp logic.Heading 3 (Gán đúng cấp)3. Lịch trình sự kiệnNormal, không định dạng gì cảMang nhãn Normal gốc, hoàn toàn bị bỏ qua khi quét mục lục.

## 2. Hậu quả của việc nhầm cấp Heading (H2 sang H3) đối với Auto TOC
Cơ chế phân cấp thụt lề (Indentation Hierarchy): Auto TOC hiển thị cấu trúc theo độ lùi đầu dòng tương ứng với cấp nhãn: Heading 1 nằm sát lề trái, Heading 2 thụt vào 1 khoảng (Tab/Indent), Heading 3 thụt vào sâu hơn nữa.Hậu quả khi gán nhầm:Dòng 2.1.1. Tiểu ban Kỹ thuật theo đánh số chỉ mục 2.1.1 bắt buộc phải là cấp con trực thuộc 2.1. Ban Nội dung (Heading 2).Nếu gán nhầm dòng 2.1. Ban Nội dung thành Heading 3 hoặc đảo lộn cấp giữa H2 và H3, trên mục lục dòng con sẽ bị đẩy ra ngang hàng hoặc nhô ra ngoài dòng cha. Điều này làm mất tính trực quan logic, khiến bộ mục lục bị sai lệch phân cấp trực quan (visual hierarchy) và không phản ánh đúng cấu trúc tài liệu.

# Phần 2: Sửa lỗi & Nghiệm thu
## Thao tác chuẩn hóa 7 dòng tiêu đề & Tạo Auto TOC
Gán heading cho các mục như 1 , 1.1 , ... phân cấp rõ ràng để auto TOC có thẻ quét dc .

## Bẫy giữ liệu : 

Hiện trạng: Khi viết thêm nội dung khiến mục "3. Lịch trình sự kiện" bị đẩy từ trang 2 sang trang 4, nếu không thực hiện thao tác cập nhật, bảng Auto TOC SẼ KHÔNG TỰ ĐỘNG CẬP NHẬT SỐ TRANG MỚI (vẫn giữ nguyên số trang cũ).

## Thao tác cần làm là : 
chọn update table .., sau đó chọn update page number only hoặc update entire table
