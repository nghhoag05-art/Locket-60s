# LOCKET ONLY 60s — HƯỚNG DẪN CÀI ĐẶT

ĐÂY LÀ BỘ MỚI CHỈ CÓ LOCKET. KHÔNG CÓ YOUTUBE.
Bộ này không tự đăng file lên GitHub. Để tránh lỗi Not Found, cần upload đủ 4 file vào đúng đường dẫn trước khi dán URL Module.

## CẤU TRÚC CHÍNH XÁC

Locket-Custom-Personal-huyhoang/
├── scripts/
│   ├── forceGold4.3_60s_full.js
│   ├── locketfix8_60s_full.js
│   └── header7_60s_full.js
└── module/
    └── locket-only-60s-full.module

## CÁCH ĐƯA LÊN GITHUB

1. Mở repo https://github.com/nghhoag05-art/Locket-Custom-Personal-huyhoang và chọn nhánh main.
2. Bấm thư mục scripts/ và upload BA file .js trong bộ ZIP. Đừng upload nguyên ZIP hoặc thêm thư mục bao ngoài. Commit.
3. Bấm thư mục module/ và upload file locket-only-60s-full.module. Commit.
4. Mở lần lượt bốn URL bên dưới bằng trình duyệt. Mỗi link phải hiển thị mã nguồn (không được hiện 404 / Not Found).

SCRIPT VIDEO/CAPTION:
https://raw.githubusercontent.com/nghhoag05-art/Locket-Custom-Personal-huyhoang/refs/heads/main/scripts/forceGold4.3_60s_full.js

SCRIPT REVENUECAT:
https://raw.githubusercontent.com/nghhoag05-art/Locket-Custom-Personal-huyhoang/refs/heads/main/scripts/locketfix8_60s_full.js

SCRIPT HEADER:
https://raw.githubusercontent.com/nghhoag05-art/Locket-Custom-Personal-huyhoang/refs/heads/main/scripts/header7_60s_full.js

MODULE:
https://raw.githubusercontent.com/nghhoag05-art/Locket-Custom-Personal-huyhoang/refs/heads/main/module/locket-only-60s-full.module

5. CHỈ khi các link mở thành công mới thêm URL MODULE vào Shadowrocket.
6. Tắt các Module Locket cũ (kể cả bản gộp YouTube), làm mới Module/Script rồi mở lại Locket.

## NỘI DUNG

- forceGold4.3_60s_full.js: giữ nguyên toàn bộ nhóm cấu hình từ bản gần nhất của bạn: camera, feature gates, filter/AI Looks, video, caption, widget, friends, chat, cache và các tùy chỉnh. 22 giá trị thời lượng 30.0 được đổi thành 60.0. Bổ sung bắt lỗi JSON.
- locketfix8_60s_full.js: mô phỏng dữ liệu Gold theo bộ cũ; không phải thanh toán thật.
- header7_60s_full.js: xử lý X-RevenueCat-ETag cho request có User-Agent Locket.
- Module chứa đúng ba đường dẫn này; không có YouTube.

## GIỚI HẠN

ĐẶT 60 GIÂY TRONG SCRIPT KHÔNG ĐỒNG NGHĨA LOCKET THỰC TẾ SẼ QUAY ĐƯỢC 60 GIÂY. Ứng dụng hoặc máy chủ có thể áp giới hạn 3 giây, hoặc từ chối tính năng do quyền tài khoản. AI Create Look cũng không tự được mở nhờ những cờ giao diện.

Lưu ý: code gốc có số điện thoại Zalo trong popup; vì repo công khai, bạn cân nhắc xóa số đó trước khi upload nếu muốn bảo mật. Tránh tin cậy Root CA từ bên thứ ba không rõ nguồn gốc.
