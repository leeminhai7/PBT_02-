Phần A:
Câu A1:
1. type="email" → Ô nhập text, kiểm tra có @ và domain → Dùng cho đăng ký tài khoản
2. type="password" → Ô nhập bị ẩn ký tự → Dùng nhập mật khẩu
3. type="number" → Ô nhập số, có nút tăng/giảm → Dùng nhập số lượng sản phẩm
4. type="tel" → Ô nhập số điện thoại → Dùng nhập SĐT khách hàng
5. type="date" → Chọn ngày từ calendar → Dùng chọn ngày sinh / ngày giao hàng
6. type="checkbox" → Ô tick chọn nhiều → Dùng chọn đồng ý điều khoản
7. type="radio" → Chọn 1 trong nhiều → Dùng chọn giới tính / phương thức thanh toán
8. type="file" → Upload file → Dùng upload ảnh đại diện / chứng từ
9. type="range" → Thanh kéo → Dùng chọn khoảng giá / số ngày giao hàng
10. type="search" → Ô tìm kiếm → Dùng tìm sản phẩm
Câu A2:
Trường hợp 1:
<input type="text" required value="">
→ Không submit được, báo lỗi "Please fill out this field"
→ Vì có thuộc tính required nhưng để trống

Trường hợp 2:
<input type="email" value="abc">
→ Không submit được
→ Vì "abc" không đúng định dạng email (thiếu @)

Trường hợp 3:
<input type="number" min="1" max="10" value="15">
→ Không submit được
→ Vì 15 > max (10)

Trường hợp 4:
<input type="text" pattern="[0-9]{10}" value="abc123">
→ Không submit được
→ Vì không đúng pattern (không đủ 10 chữ số)

Trường hợp 5:
<input type="password" minlength="8" value="123">
→ Không submit được
→ Vì độ dài < 8 ký tự
Câu A3:
<label for="email"> quan trọng vì:
Giúp screen reader đọc đúng tên trường
Khi click vào label → focus vào input
Tăng khả năng sử dụng cho người khiếm thị

Khi dùng <fieldset> + <legend>:
<fieldset>
  <legend>Thông tin cá nhân</legend>
  <input type="text">
  <input type="email">
</fieldset>

aria-label dùng khi:
Không có <label> hiển thị
Không nên dùng khi đã có <label> vì:
Bị trùng thông tin
Gây rối cho screen reader

Câu A4:
loading="lazy":
Chỉ load ảnh khi cuộn tới
Giúp tăng tốc độ load trang

Không nên dùng khi:
Ảnh quan trọng (ảnh banner đầu trang)

Nhiều <source> trong <video> vì:
Trình duyệt hỗ trợ format khác nhau

Thuộc tính alt:
Mô tả ảnh khi ảnh lỗi hoặc cho screen reader
iPhone:
alt="iPhone 16 Pro Max 256GB màu Titan"
Ảnh trang trí:
alt=""
Biểu đồ:
alt="Biểu đồ doanh thu quý 1 năm 2026 tăng 20%"

Câu A5:
Cách 1 (<img>):
Dùng khi ảnh đơn giản, không cần chú thích
Ví dụ:
Avatar người dùng
Icon sản phẩm

Cách 2 (<figure> + <figcaption>):
Dùng khi ảnh cần mô tả / chú thích
Ví dụ:
Ảnh sản phẩm kèm giá
Ảnh biểu đồ kèm giải thích

Phần C:
Câu C1:
Lỗi 1: Dòng 2 — Input "Tên" không có <label for="">
Sửa:
<label for="name">Tên:</label>
<input type="text" id="name" name="name" required><br><br>

Lỗi 2: Input email không có label
Sửa:
<label for="email">Email:</label>
<input type="email" id="email" name="email" required placeholder="Email của bạn"><br><br>

Lỗi 3: Password không có label
Sửa:
<label for="pass">Mật khẩu:</label>
<input type="password" id="pass" name="pass" required minlength="8"><br><br>

Lỗi 4: Confirm password không có label và không có name
Sửa:
<label for="confirm">Nhập lại mật khẩu:</label>
<input type="password" id="confirm" name="confirm" required minlength="8"><br><br>

Lỗi 5: Phone dùng type="text" (sai semantic)
Sửa:
<label for="phone">SĐT:</label>
<input type="tel" id="phone" name="phone" pattern="[0-9]{10}" required><br><br>
Lỗi 6: Input phone có sẵn value → không nên (user phải tự nhập)
Sửa: bỏ value

Lỗi 7: <select> không có label và name
Sửa:
<label for="city">Thành phố:</label>
<select id="city" name="city">
  <option>Hà Nội</option>
  <option>TP.HCM</option>
</select><br><br>

Lỗi 8: Checkbox điều khoản không có input và không required
Sửa:
<label>
  <input type="checkbox" name="agree" required>
  Tôi đồng ý điều khoản
</label>

Câu C2:
1.Regex pattern
CMND/CCCD (12 số):
pattern="[0-9]{12}"
Số tài khoản (10-15 số):
pattern="[0-9]{10,15}"

2.HTML k đủ an toàn
Vì:
Chỉ chạy phía client (trình duyệt)
User có thể:
Tắt validation
Sửa code bằng DevTools
Gửi request giả (Postman)

3.3 validation HTML KHÔNG làm được
So sánh 2 trường (password = confirm password)
Kiểm tra dữ liệu tồn tại (email đã đăng ký chưa)
Logic phức tạp (VD: tuổi >= 18 dựa vào ngày sinh)

4.2 rủi ro bảo mật nếu chỉ validate frontend
Hacker bypass validation → gửi dữ liệu sai / độc hại
SQL Injection / dữ liệu rác → phá hệ thống
