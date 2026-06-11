# Hai Thư Viện — đọc & tải truyện theo chương

Một trang web tĩnh đơn giản, chạy miễn phí trên **GitHub Pages**. Trang chủ có **2 thư viện**:

- **OurEra** (Trái Đất)
- **High and Higher** (Mythren)

Mỗi thư viện chứa nhiều **bộ truyện**, mỗi bộ truyện chia thành nhiều **phần**, mỗi phần có
nhiều **chương**. Có một **Timeline** ở đầu trang — bấm vào một mục sẽ tự mở đúng bộ
truyện/phần và cuộn thẳng tới chương đó, kèm nút tải file Word (.docx).

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

> Lưu ý: vì đây là trang tĩnh, "tải file lên" nghĩa là **thêm file vào repo trên GitHub**,
> chứ không có ô upload trực tiếp trên trang.

### 1. Thêm một CHƯƠNG mới (vào bộ truyện/phần đã có)
1. Mở thư mục `chapters/<thư viện>/<bộ-truyện>/<phần>/` → **Add file → Upload files** → kéo
   file `.docx` vào → Commit.
2. Mở `index.html`, tìm khối `===== KHỐI MẪU 1 CHƯƠNG =====` bên trong `<section class="library" id="ourera">`
   hoặc `id="mythren"` (tuỳ thư viện), trong đúng bộ truyện/phần cần thêm.
3. Copy nguyên khối `<li class="chapter" id="..."> ... </li>`, dán **lên trên cùng** danh sách
   `<ol class="chapters">` (chương mới nhất nằm đầu).
4. Sửa: `id` (đặt tên duy nhất, không trùng với chương khác — ví dụ `ourera-mau-p1-c4`),
   ngày tháng, tên chương, mô tả, và đường dẫn `href="chapters/..."`.
5. (Khuyến khích) Thêm 1 mục mới vào **Timeline** ở đầu trang: copy khối
   `===== KHỐI MẪU 1 MỤC TIMELINE =====`, dán lên trên cùng `<ol class="timeline">`, sửa nội
   dung và đặt `href="#id-cua-chuong-vua-tao"` (phải trùng với `id` ở bước 4).
6. Commit. Trang sẽ tự cập nhật sau khoảng 1 phút.

### 2. Thêm một PHẦN mới (trong một bộ truyện đã có)
1. Tạo thư mục `chapters/<thư viện>/<bộ-truyện>/<phần-mới>/` rồi tải file `.docx` chương đầu
   tiên của phần lên đó.
2. Trong `index.html`, copy khối `===== KHỐI MẪU 1 PHẦN =====` (một thẻ `<details class="part">`),
   dán vào trong `<div class="series__body">` của bộ truyện tương ứng.
3. Sửa tên phần (`.part__name`) và các chương bên trong như hướng dẫn ở mục 1.

### 3. Thêm một BỘ TRUYỆN mới (trong một thư viện đã có)
1. Tạo thư mục `chapters/<thư viện>/<bộ-truyện-mới>/<phần-1>/` rồi tải file `.docx` lên.
2. Trong `index.html`, copy khối `===== KHỐI MẪU 1 BỘ TRUYỆN =====` (một thẻ `<details class="series">`),
   dán vào trong `<section class="library" id="ourera">` (hoặc `id="mythren"`).
3. Sửa tên bộ truyện (`.series__name`), mô tả (`.series__desc`) và phần/chương bên trong.

## Tuỳ chỉnh nhanh
- **Tên trang / lời giới thiệu:** sửa trong khối `<header class="hero">` ở đầu `index.html`.
- **Tên & mô tả 2 thư viện ở trang chủ:** sửa trong khối `<nav class="lib-grid">`.
- **Màu sắc:** sửa các biến màu trong phần `:root{ ... }` (ví dụ `--lamp` là màu vàng đèn).
- **Tiêu đề tab trình duyệt:** sửa trong thẻ `<title>`.

Không cần cài đặt gì cả — chỉ là một file HTML.
