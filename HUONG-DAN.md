# Hướng dẫn quản lý website CKM

Website gồm 2 trang:

- **`index.html`** — trang chính khách hàng xem: https://huycdt06.github.io/CKM-website/
- **`admin.html`** — trang quản lý để thêm/sửa ảnh và mô tả: https://huycdt06.github.io/CKM-website/admin.html

Nội dung các dự án được lưu trong file **`content.json`**. Bạn không cần chỉnh file này bằng tay — trang `admin.html` sẽ tự cập nhật nó.

---

## Phần 1 — Tạo "khóa truy cập" GitHub (chỉ làm 1 lần)

Trang quản lý cần một "khóa" để được phép lưu thay đổi lên GitHub.

1. Đăng nhập GitHub (tài khoản **huycdt06**).
2. Vào: **Settings** → **Developer settings** → **Personal access tokens** → **Fine-grained tokens** → **Generate new token**.
   (Đường dẫn nhanh: https://github.com/settings/tokens?type=beta)
3. Điền:
   - **Token name:** `CKM admin`
   - **Expiration:** chọn thời hạn (ví dụ 90 ngày hoặc 1 năm).
   - **Repository access:** chọn **Only select repositories** → chọn **`CKM-website`**.
   - **Permissions** → **Repository permissions** → tìm **Contents** → chọn **Read and write**.
4. Bấm **Generate token** và **sao chép** chuỗi khóa (bắt đầu bằng `github_pat_...`).
   ⚠️ Chỉ hiện 1 lần — lưu lại cẩn thận.

---

## Phần 2 — Dùng trang quản lý

1. Mở https://huycdt06.github.io/CKM-website/admin.html
2. Dán khóa vừa tạo vào ô, bấm **Kết nối & tải nội dung**.
   (Khóa chỉ lưu trong trình duyệt máy bạn, lần sau không cần dán lại.)
3. Với mỗi dự án bạn có thể:
   - Sửa **tên**, **nhãn loại**, **mô tả**.
   - **Chọn ảnh** từ máy tính (hoặc dán đường dẫn ảnh có sẵn).
   - **Xóa ảnh** → website sẽ hiện ô giữ chỗ thay cho ảnh.
   - Sắp xếp thứ tự bằng nút ▲ ▼, hoặc **Xóa** dự án.
   - Bấm **➕ Thêm dự án mới** để thêm.
4. Xong bấm **💾 Lưu & đăng lên website**.
5. Chờ khoảng **1 phút**, website chính sẽ tự cập nhật.

---

## Lưu ý

- Ảnh nên nhỏ hơn 8MB. Ảnh nằm ngang (tỷ lệ 16:9) hiển thị đẹp nhất.
- Nếu báo lỗi *"Khóa không hợp lệ"*: khóa đã hết hạn → tạo khóa mới (Phần 1).
- Muốn đổi giao diện, màu sắc, thêm trang mới: nhờ hỗ trợ kỹ thuật.
- Nút **"Quên khóa"** ở góc trên xóa khóa khỏi trình duyệt (dùng khi đổi máy).
