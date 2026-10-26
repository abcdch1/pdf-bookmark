# Gắn Bookmark PDF

Trang web tĩnh (chạy được trên GitHub Pages) để gắn mục lục/bookmark vào file PDF từ một file JSON. Mọi xử lý chạy trong trình duyệt bằng [pdf-lib](https://pdf-lib.js.org/), file PDF không được tải lên máy chủ nào.

## Cách dùng
1. Mở trang, kéo thả file PDF.
2. Kéo thả file bookmark JSON (hoặc bấm "Dùng file mẫu").
3. Chỉnh độ lệch trang (offset) nếu số trang in trong sách khác số trang thực của PDF.
4. Bấm "Tạo PDF có bookmark" để tải file `<tên>_bookmark.pdf`.

## Định dạng JSON
```json
{
  "schema": "pdf-bookmarks/1",
  "title": "Tên tài liệu",
  "offset": 0,
  "bookmarks": [
    {"title": "CHƯƠNG 1", "page": 4, "level": 1},
    {"title": "1.1. Đại cương", "page": 4, "level": 2}
  ]
}
```
- `page`: số trang (trang thực trong PDF = `page` + `offset`).
- `level`: 1 = chương, 2 = mục, 3 = tiểu mục…
- Xem `bookmarks_mau.json` để có ví dụ đầy đủ.

## Đưa lên GitHub Pages
1. Tạo repository mới trên GitHub (ví dụ `pdf-bookmark`), đẩy toàn bộ thư mục này lên nhánh `main`.
2. Vào **Settings → Pages**, mục *Source* chọn **Deploy from a branch**, nhánh `main`, thư mục `/ (root)`, bấm Save.
3. Sau 1–2 phút trang có ở `https://<tên-github>.github.io/pdf-bookmark/`.
