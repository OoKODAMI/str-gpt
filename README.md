# Trang truyện — đọc & tải về theo chương

Một trang web tĩnh đơn giản, chạy miễn phí trên **GitHub Pages**. Mỗi chương hiển thị trên một
"timeline" và có nút tải file Word (.docx) về máy.

## Cấu trúc thư mục
```
.
├── index.html        ← toàn bộ trang web (chỉnh sửa file này)
├── README.md
└── chapters/         ← BỎ TẤT CẢ FILE .docx VÀO ĐÂY
    ├── chuong-01.docx
    ├── chuong-02.docx
    └── chuong-03.docx
```

## Cách đưa lên mạng (làm 1 lần)
1. Tạo một repository mới trên GitHub (ví dụ tên `truyen`).
2. Kéo–thả tất cả file ở đây (`index.html`, thư mục `chapters/`...) vào repo rồi **Commit**.
3. Vào **Settings → Pages**. Mục *Source* chọn nhánh `main`, thư mục `/ (root)`, bấm **Save**.
4. Đợi 1–2 phút, GitHub sẽ cho bạn một địa chỉ dạng
   `https://<tên-của-bạn>.github.io/truyen/` — đó là trang web của bạn.

## Cách thêm một chương mới
> Lưu ý: vì đây là trang tĩnh, "tải file lên" nghĩa là **thêm file vào repo trên GitHub**,
> chứ không có ô upload trực tiếp trên trang (trang tĩnh không lưu được file người dùng gửi).
> Bù lại: miễn phí, nhanh, không cần máy chủ.

Mỗi lần có chương mới, làm 2 việc:

**1. Tải file Word lên thư mục `chapters/`**
   - Trên GitHub: mở thư mục `chapters/` → **Add file → Upload files** → kéo file .docx vào → Commit.

**2. Thêm một mục vào `index.html`**
   - Mở `index.html`, tìm khối có ghi `===== KHỐI MẪU 1 CHƯƠNG =====`.
   - Copy nguyên khối `<li class="entry"> ... </li>`, dán lên trên cùng (để chương mới nằm đầu).
   - Sửa: ngày tháng, tên chương, mô tả, và đường dẫn file trong `href="chapters/..."`.
   - Commit. Trang sẽ tự cập nhật sau khoảng 1 phút.

## Tuỳ chỉnh nhanh
- **Tên truyện / lời giới thiệu:** sửa trong khối `<header class="hero">` ở đầu `index.html`.
- **Màu sắc:** sửa các biến màu trong phần `:root{ ... }` (ví dụ `--lamp` là màu vàng đèn).
- **Tiêu đề tab trình duyệt:** sửa trong thẻ `<title>`.

Không cần cài đặt gì cả — chỉ là một file HTML.
