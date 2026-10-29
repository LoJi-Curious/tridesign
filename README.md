# QUAN NIỆM THIẾT KẾ CỦA TÔI — HTML/CSS/JS thuần (không GSAP, không API, không backend)

## Chạy trên VS Code
1. Mở thư mục `design-philosophy` bằng VS Code.
2. Cài extension **Live Server** → chuột phải `index.html` → *Open with Live Server* (hoặc double-click `index.html`).
3. Cần internet cho font Google (Be Vietnam Pro, JetBrains Mono); offline sẽ dùng font hệ thống.

## Cấu trúc
- `index.html` — khung: mở đầu, vòng tròn chủ đề, panel nội dung
- `css/style.css` — màu (đầu file), nút, layout, hiệu ứng, responsive
- `js/content.js` — **9 nội dung, đường dẫn nhân vật, màu nhấn, icon từng chương**
- `js/main.js` — logic: mở đầu/bỏ qua/phát lại, vòng tròn, chuyển chương, phím tắt, parallax, bí mật
- `assets/images/character.png` — nhân vật (PNG nền trong suốt, 300×272)

## Đổi nhân vật
Đặt ảnh vào `assets/images/`, sửa `characterSrc` trong `js/content.js`. Nên dùng PNG/WebP nền trong suốt, cạnh dài ≥ 1000px cho nét (ảnh hiện tại nhỏ nên hơi mờ khi phóng to). Ảnh lỗi/thiếu → hiện hình SVG thay thế.

## Đổi màu / icon / chữ
- Màu nền: `:root` trong `css/style.css`. Màu và icon từng chương: `CONFIG.accents`, `CONFIG.icons`.
- Chữ chủ đề: `CHAPTERS` trong `js/content.js` (`t` tiêu đề, `b` nội dung; câu đầu tự thành câu chủ đạo).

## Tương tác
Vòng 9 nút tự mở sau phần mở đầu; bấm nhân vật hoặc nút tròn cạnh thanh mô tả để thu/mở. Rê chuột (hoặc chạm lần 1 trên điện thoại) để xem tên chủ đề, bấm lần nữa hoặc "Mở chương" để vào. Phím: `←/→`, `Esc`, `1–9`, `M`. Dải số bên phải panel là menu nhanh. Bí mật: bấm logo **TRÍ®** 5 lần liên tiếp.

## Checklist kiểm thử
- [ ] Mở đầu ~3.8s, "Bỏ qua" hoạt động, nút ↺ phát lại
- [ ] Vòng tròn bung ra; rê/chạm đổi màu đĩa nhân vật, dải chữ và thanh mô tả
- [ ] Mở từng chương 1–9: chữ hiện đủ, icon vẽ nét, Trước/Sau/Kết thúc, Về danh sách, ✕, Esc, phím 1–9
- [ ] Đổi tên `character.png` tạm thời → thấy hình thay thế
- [ ] F12 → Console không lỗi; thử giả lập điện thoại ≤ 400px
- [ ] Bật "Reduce motion" của hệ điều hành → bỏ qua mở đầu, chữ vẫn hiện
