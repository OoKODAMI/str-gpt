# Thư viện — đọc & tải truyện theo chương

Một trang web tĩnh đơn giản, chạy miễn phí trên **GitHub Pages**. Trang có:

- **2 thẻ thư viện** ở đầu trang: **OurEra** và **High and Higher** (bấm để nhảy thẳng tới
  bìa truyện thuộc thư viện đó).
- **Timeline bìa truyện**: mỗi mục là một "bìa" đại diện cho một **phần truyện** (ví dụ
  `OurEra — Bộ truyện mẫu — Phần 1`). Bấm vào bìa → mở ra danh sách các chương bên trong,
  mỗi chương có nút tải file Word (.docx).

## Cấu trúc thư mục
```
.
├── index.html        ← toàn bộ trang web (chỉnh sửa file này)
├── README.md
└── chapters/
    ├── ourera/                  ← truyện thuộc thư viện OurEra
    │   └── bo-truyen-mau/       ← 1 bộ truyện
    │       └── phan-1/          ← 1 phần trong bộ truyện
    │           ├── chuong-01.docx
    │           ├── chuong-02.docx
    │           └── chuong-03.docx
    └── mythren/                 ← truyện thuộc thư viện High and Higher
        └── bo-truyen-mau/
            └── phan-1/
                └── chuong-01.docx
```

## Cách đưa lên mạng (làm 1 lần)
1. Tạo một repository mới trên GitHub (ví dụ tên `truyen`).
2. Kéo–thả tất cả file ở đây (`index.html`, thư mục `chapters/`...) vào repo rồi **Commit**.
3. Vào **Settings → Pages**. Mục *Source* chọn nhánh `main`, thư mục `/ (root)`, bấm **Save**.
4. Đợi 1–2 phút, GitHub sẽ cho bạn một địa chỉ dạng
   `https://<tên-của-bạn>.github.io/truyen/` — đó là trang web của bạn.

## Cách thêm nội dung mới

### 1. Thêm một CHƯƠNG mới vào bìa truyện đã có
1. Tải file `.docx` lên `chapters/<thư viện>/<bộ-truyện>/<phần>/`.
2. Mở `index.html`, tìm đúng `<li class="entry" id="...">` của bìa truyện đó.
3. Trong `<ol class="chapters">`, copy khối `===== KHỐI MẪU 1 CHƯƠNG =====` (một thẻ
   `<li class="chapter">`), dán **lên trên cùng** danh sách (chương mới nhất ở trên).
4. Sửa: ngày, tên chương, mô tả, và đường dẫn `href="chapters/..."`.
5. Cập nhật `cover__meta` ở bìa (số chương · ngày cập nhật).
6. Commit. Trang sẽ tự cập nhật sau khoảng 1 phút.

### 2. Thêm một BÌA TRUYỆN MỚI (một phần truyện mới)
1. Tạo thư mục `chapters/<thư viện>/<bộ-truyện>/<phần-mới>/` và tải các file `.docx` chương vào.
2. Trong `index.html`, copy nguyên khối `===== KHỐI MẪU 1 BÌA TRUYỆN =====` (một thẻ
   `<li class="entry">` chứa `<details class="cover">`), dán **lên trên cùng** `<ol class="timeline">`
   (bìa mới nhất ở trên).
3. Sửa:
   - `id="..."` — đặt tên duy nhất (vd `ourera-bo-A-p2`).
   - `cover__lib` — tên thư viện hiển thị (`OurEra` hay `High and Higher`).
   - `cover__title` — tên bộ truyện và phần.
   - `cover__meta` — số chương · ngày cập nhật.
   - Danh sách `<li class="chapter">` bên trong (xem mục 1).

## Tuỳ chỉnh nhanh
- **Tiêu đề trang ("Thư viện"):** sửa trong `<h1 class="hero__title">`.
- **Tên 2 thẻ thư viện:** sửa trong khối `<nav class="lib-grid">`.
- **Màu sắc:** sửa các biến màu trong phần `:root{ ... }` (vd `--lamp` là màu vàng đèn).
- **Tiêu đề tab trình duyệt:** sửa trong thẻ `<title>`.

Không cần cài đặt gì cả — chỉ là một file HTML.
