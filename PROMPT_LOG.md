# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Nguyễn Thị Tuyết Ngân
- **MSSV:** 125001247
- **Tên đề tài Website:** TUYẾT NGÂN ATELIER - Website Thời Trang Nữ & Váy Đầm Thiết Kế Cao Cấp
- **Công cụ AI đã sử dụng:** Antigravity (Powered by DeepMind Gemini 3.8 Flash)

---

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> *"Hãy đóng vai trò là một chuyên gia Lập trình Front-End và Chuyên viên Thiết kế UI/UX Thời trang Nữ Cao cấp (Feminine Couture Designer). Tôi cần tạo một website bán và may đo váy đầm thiết kế mang tên tôi là **'TUYẾT NGÂN ATELIER'**, với tone màu chủ đạo là **Màu hồng (Pastel Pink / Rose Gold / Pearl White)** ngọt ngào, kiêu kỳ và sang trọng.*
>
> *Website phải kế thừa cấu trúc kỹ thuật từ Buổi 5 và tuân thủ nghiêm ngặt các tiêu chí sau:*
> 1. *Chuẩn Semantic HTML5: Bắt buộc dùng đúng ngữ nghĩa các thẻ `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<address>`, tuyệt đối không lạm dụng thẻ `<div>` vô nghĩa.*
> 2. *CSS Variables & Thiết kế thẩm mỹ: Khai báo hệ thống biến `:root` quản lý màu sắc tone hồng thượng lưu (Blush Pink `#fdf2f8`, Rose Petal `#ec4899`, Velvet Rose `#be185d`, Pearl White `#ffffff`), font chữ thời trang ('Playfair Display', 'Plus Jakarta Sans'), spacing và bo góc radius mềm mại.*
> 3. *Tối ưu hóa Responsive: Căn chỉnh hoàn hảo trên cả máy tính (Desktop) và điện thoại di động (Mobile) bằng CSS Flexbox và CSS Grid.*
> 4. *Thư viện & Hiệu ứng: Tích hợp Animate.css cho tiêu đề/nút CTA, hiệu ứng `:hover`, `:focus` tự viết bằng CSS, thẻ 3D Flip Card lật mặt trước/sau giới thiệu chất liệu tơ tằm & dạ Tweed (Bài 2), Banner Parallax (Bài 4), Nút Floating Action Button (Bài 1).*
> 5. *TUYỆT ĐỐI KHÔNG DÙNG JAVASCRIPT: Toàn bộ tương tác bao gồm thanh Hamburger Menu Mobile phải hoạt động 100% bằng kỹ thuật CSS Checkbox Hack của Bài 5."*

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML5 & Bảng màu CSS Variables Tone Hồng
- **Prompt đã dùng:**
  > *"Khởi tạo cấu trúc HTML5 chuẩn ngữ nghĩa cho thương hiệu thời trang nữ 'TUYẾT NGÂN ATELIER'. Phân chia rõ ràng các phân khu: `<header>` chứa logo monogram TN và menu điều hướng; `<main>` chứa Hero Section, giá trị cốt lõi, danh mục thời trang nữ, danh sách sản phẩm bằng thẻ `<article>`, khu vực vải 3D Flip Card, quy trình may đo 5 bước, trích dẫn Parallax, đánh giá khách hàng và form đặt lịch hẹn; cuối cùng là `<footer>` chứa thông tin showroom và bản quyền mang tên Nguyễn Thị Tuyết Ngân (MSSV: 125001247). Xây dựng hệ thống biến `:root` tone màu hồng pastel quyến rũ, nữ tính."*
- **Kết quả AI tạo ra:**
  - AI đã tạo ra khung HTML phân tầng rõ ràng, bảng màu hồng được phối rất dịu mắt và quý phái giữa màu hồng cánh sen, hồng phấn và ánh nhũ vàng hồng.
  - Tuy nhiên, một số thẻ sản phẩm ban đầu bị lạm dụng thẻ `<div>` lồng nhau.
- **Nhận xét & Tinh chỉnh của SV:**
  - Nhắc AI chuẩn hóa toàn bộ thẻ bao quanh sản phẩm thành `<article class="product-card">`.
  - Thay đổi phần chân trang liên hệ sử dụng thẻ `<address>` chuẩn W3C thay vì danh sách `<ul>` thông thường.

---

### Lần 2: Tích hợp thư viện Animate.css & Typography Tiếng Việt chuẩn
- **Prompt đã dùng:**
  > *"Nhúng thư viện Animate.css từ cdnjs vào dự án. Hãy gắn các class animation của Animate.css (`animate__animated`, `animate__fadeInDown`, `animate__fadeInUp`, `animate__pulse`) vào phần Text tiêu đề, Badge danh vị, và Nút CTA Đặt May Nàng Thơ trên Hero Section. Đồng thời, cấu hình font chữ Playfair Display và Plus Jakarta Sans hỗ trợ 100% Tiếng Việt có dấu, không bị lỗi font khi hiển thị tên 'Nguyễn Thị Tuyết Ngân'."*
- **Thách thức gặp phải:**
  - Một số font chữ phong cách Gothic/La Mã cổ điển thường không có dấu tiếng Việt (bị lỗi ký tự `ễ`, `ệ`, `ư`, `ơ`).
- **Cách sửa prompt (Debug prompt):**
  - Chỉ định rõ ràng bộ đôi font Google Fonts: `Playfair Display` (font chữ có chân thanh lịch của các tạp chí Vogue, Harper's Bazaar) và `Plus Jakarta Sans` (font không chân hiện đại), cả hai đều hỗ trợ đầy đủ bộ ký tự Tiếng Việt.

---

### Lần 3: Xây dựng Menu Mobile bằng CSS Checkbox Hack (Không Dùng JavaScript)
- **Prompt đã dùng:**
  > *"Quy chế bài thi yêu cầu tuyệt đối KHÔNG được sử dụng JavaScript. Hãy hiện thực hóa thanh Menu Hamburger trên điện thoại hoàn toàn bằng kỹ thuật CSS Checkbox Hack của Bài 5: sử dụng `<input type="checkbox" id="menu-toggle" class="menu-checkbox">` và `<label for="menu-toggle" class="hamburger-btn">`. Khi bấm vào nút 3 gạch, menu trượt xuống êm ái và 3 thanh biến hình thành dấu X mà không cần bất kỳ một dòng code JS nào."*
- **Kết quả AI tạo ra & Tinh chỉnh của SV:**
  - Menu mobile hoạt động trơn tru:
    * Trên desktop: Nút 3 gạch ẩn đi (`display: none`), menu dàn ngang bằng Flexbox.
    * Trên mobile: Nút 3 gạch màu hồng cánh sen xuất hiện ở góc phải. Khi chạm vào `<label>`, trạng thái `:checked` của checkbox kích hoạt `transform: translateY(0)`, menu trượt xuống từ thanh header, 3 thanh xoay 45° thành dấu `X`. Chạm lại lần nữa để thu gọn.
  - Toàn bộ website đạt chuẩn 100% HTML5 & CSS3 thuần khiết, 0 lỗi W3C, mở tốt trên mọi thiết bị.

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

### AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?
1. **Khởi tạo nội dung mẫu thời trang nữ chuyên nghiệp:** Thay vì mất hàng giờ tự tìm kiếm và nghĩ ra tên các dòng vải thời trang cao cấp (Mulberry Silk 19 momme, French Tweed de Paris, Royal Organza), các thuật ngữ may đo thời trang (Draping 3D, Puff sleeve, Pleated skirt), AI đã tự động điền sẵn hệ thống dữ liệu chân thực và mang đậm phong thái thời trang tiểu thư, nàng thơ.
2. **Thiết lập bảng màu CSS Variables nhất quán:** AI hỗ trợ phối màu hồng pastel chuyển tiếp hài hòa từ nền `#fff8fa` đến các điểm nhấn `#ec4899` và `#be185d`, giúp giao diện vừa ngọt ngào, dịu dàng nhưng không bị chói gắt hay sến súa.
3. **Hiện thực hóa tương tác phức tạp bằng CSS thuần:** Giúp viết chuẩn xác các bộ chọn nâng cao như `#menu-toggle:checked ~ .nav-menu-wrapper` và hiệu ứng lật thẻ 3D `.flip-card-wrapper:hover .flip-card-inner` đúng chuẩn đề thi mà không cần dùng đến JavaScript.

### Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?
1. **Rõ ràng về mặt ràng buộc kỹ thuật (Constraints):** Việc quy định rõ ngay từ đầu *"Không dùng JavaScript", "Tone màu hồng pastel", "Tên sinh viên Nguyễn Thị Tuyết Ngân"* giúp AI không tự ý thêm các thư viện hay mã script ngoài yêu cầu của giáo viên.
2. **Kỹ năng kiểm tra và tinh chỉnh liên tục (Iteration):** Trong quá trình Vibe Coding, sinh viên cần kiểm tra kỹ từng chi tiết trên màn hình điện thoại (F12 Responsive Mode) để kịp thời chỉ đạo AI tối ưu kích thước nút bấm, khoảng cách dòng và đảm bảo menu đóng mở ổn định trên mọi kích thước màn hình.
