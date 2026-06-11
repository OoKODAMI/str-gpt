# Thư viện — đọc & tải truyện theo phần

Một trang web tĩnh đơn giản, chạy miễn phí trên **GitHub Pages**. Trang có:

- **2 thư viện**: **OurEra** và **High and Higher**. Bấm vào tên thư viện để mở danh sách
  các **phần** (Phần 1, Phần 2, Phần 3...), mỗi phần có nút tải file Word (.docx).
- **Timeline**: bấm vào ô "Timeline" ở đầu trang để mở một hàng ngang thể hiện **thứ tự đọc
  gợi ý** của tác giả (ví dụ: OurEra Phần 1 → High and Higher Phần 1 → OurEra Phần 2 → ...).
  Bấm vào một bước sẽ mở đúng thư viện và cuộn tới phần đó.

## Cấu trúc thư mục
```
.
├── index.html        ← toàn bộ trang web (chỉnh sửa file này)
├── README.md
└── chapters/
    ├── ourera/                  ← truyện thuộc thư viện OurEra
    │   └── bo-truyen-mau/       ← 1 bộ truyện
    │       ├── phan-1.docx
    │       ├── phan-2.docx
    │       └── phan-3.docx
    └── mythren/                 ← truyện thuộc thư viện High and Higher
        └── bo-truyen-mau/
            ├── phan-1.docx
            ├── phan-2.docx
            └── phan-3.docx
```

## Cách đưa lên mạng (làm 1 lần)
1. Tạo một repository mới trên GitHub (ví dụ tên `truyen`).
2. Kéo–thả tất cả file ở đây (`index.html`, thư mục `chapters/`...) vào repo rồi **Commit**.
3. Vào **Settings → Pages**. Mục *Source* chọn nhánh `main`, thư mục `/ (root)`, bấm **Save**.
4. Đợi 1–2 phút, GitHub sẽ cho bạn một địa chỉ dạng
   `https://<tên-của-bạn>.github.io/truyen/` — đó là trang web của bạn.

## Cách thêm nội dung mới

### 1. Thêm một PHẦN mới vào một thư viện đã có
1. Tải file `.docx` lên `chapters/<thư viện>/<bộ-truyện>/phan-N.docx`.
2. Mở `index.html`, tìm `<ol class="parts">` của thư viện tương ứng (`OurEra` hoặc
   `High and Higher`).
3. Copy khối `===== KHỐI MẪU 1 PHẦN =====` (một thẻ `<li class="part" id="...">`), dán vào
   cuối (hoặc đúng vị trí mong muốn trong) danh sách.
4. Sửa:
   - `id="..."` — đặt tên duy nhất (vd `ourera-bo-A-p4`).
   - `part__name` — tên phần hiển thị (vd "Phần 4").
   - `href="chapters/..."` — đường dẫn tới file `.docx` vừa tải lên.
5. Commit. Trang sẽ tự cập nhật sau khoảng 1 phút.

### 2. Thêm/sửa thứ tự đọc trong Timeline
1. Trong `index.html`, tìm khối `<div class="timeline-row">`.
2. Mỗi bước là một `<a class="timeline-step" href="#id-cua-phan">`, giữa các bước là
   `<span class="timeline-arrow">→</span>`.
3. Copy khối `===== KHỐI MẪU 1 BƯỚC =====` để thêm bước mới, đặt `href="#..."` trỏ tới đúng
   `id` của phần (đã đặt ở mục 1), và sắp xếp các bước theo đúng thứ tự bạn muốn người đọc đi qua.

## Tuỳ chỉnh nhanh
- **Tiêu đề trang ("Thư viện"):** sửa trong `<h1 class="hero__title">`.
- **Tên 2 thư viện:** sửa trong `<h2 class="lib-card__title">`.
- **Màu sắc:** sửa các biến màu trong phần `:root{ ... }` (vd `--lamp` là màu vàng đèn).
- **Tiêu đề tab trình duyệt:** sửa trong thẻ `<title>`.

Không cần cài đặt gì cả — chỉ là một file HTML.
