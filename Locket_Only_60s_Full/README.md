# Locket 3 phút (180 giây) + YouTube — Shadowrocket

Repo có hai lựa chọn:

- `module/locket-60s-youtube-huyhoang.module`: Locket 3 phút kèm phần YouTube lấy từ [module đã chọn](https://github.com/nghhoag05-art/Locket-Custom-Personal-huyhoang/blob/main/module/locket-youtube-huyhoang.module).
- `module/locket-only-60s-full.module`: chỉ Locket 3 phút.

Tên repo, thư mục và file còn chứa `60s` để giữ nguyên URL đã cài. Thời lượng cấu hình hiện tại là 180 giây; `timeout=60` là giới hạn chạy script và được giữ nguyên.

## Cài bản Locket 3 phút + YouTube

1. Thêm URL sau trong phần Module của Shadowrocket:

   https://raw.githubusercontent.com/nghhoag05-art/Locket-60s/refs/heads/main/Locket_Only_60s_Full/module/locket-60s-youtube-huyhoang.module

2. Bật module mới. Tắt các module Locket và YouTube cũ có cùng quy tắc để tránh chạy trùng.
3. Trong cấu hình đang dùng, bật HTTPS Decryption/MITM. Nếu chưa có CA của riêng bạn, tạo CA trong Shadowrocket, cài chứng chỉ và bật tin cậy trong cài đặt iOS.
4. Làm mới module và các script, kết nối lại Shadowrocket rồi mở lại Locket/YouTube.
5. Kiểm tra nhật ký tải script và lỗi JavaScript trên thiết bị. URL tải thành công chưa xác nhận tính năng trong ứng dụng hoạt động.

## Nội dung bản ghép

- Đặt 22 giá trị thời lượng trong script cấu hình Locket thành `180.0` (3 phút). Tên file và URL `*_60s_full.js` được giữ để các module đã cài tiếp tục cập nhật.
- Giữ quy tắc YouTube chặn UDP/QUIC, bốn URL Rewrite, một Map Local và ba script hook từ module nguồn.
- Giữ `captionLang: "vi"`, `blockUpload: true`, `blockImmersive: true`, `blockShorts: false` và `debug: false`.
- Giữ `requires-body`, `max-size`, `binary-body-mode` và định dạng JSON argument của nguồn Maasea.
- Gộp hostname MITM của Locket và YouTube vào một mục.
- Bỏ User-Agent Locket áp dụng toàn cục.
- Bỏ quy tắc `ctier` của module nguồn vì biểu thức đó yêu cầu chuỗi dấu phẩy `,ctier,` trong URL; không thêm quy tắc thay thế chưa kiểm chứng.

## Đường dẫn script

### Locket

- https://raw.githubusercontent.com/nghhoag05-art/Locket-60s/refs/heads/main/Locket_Only_60s_Full/scripts/forceGold4.3_60s_full.js
- https://raw.githubusercontent.com/nghhoag05-art/Locket-60s/refs/heads/main/Locket_Only_60s_Full/scripts/locketfix8_60s_full.js
- https://raw.githubusercontent.com/nghhoag05-art/Locket-60s/refs/heads/main/Locket_Only_60s_Full/scripts/header7_60s_full.js

### YouTube

- https://raw.githubusercontent.com/Maasea/sgmodule/master/Script/Youtube/youtube.response.js
- https://raw.githubusercontent.com/Maasea/sgmodule/master/Script/Youtube/youtube.request.js

Script YouTube tiếp tục được tải từ Maasea/sgmodule, giấy phép Apache-2.0. Mã nguồn request có thể chuyển hướng `initplayback` đến `https://init-stream.maasea.workers.dev/`; đây là phụ thuộc có sẵn từ upstream.

## Giới hạn đã biết

- Locket: đặt các trường thời lượng 180 giây không bảo đảm ứng dụng quay hoặc máy chủ nhận video 180 giây. Dữ liệu Gold trong script là mô phỏng, không tạo giao dịch mua thật.
- Phản hồi Firebase `NO_CHANGE` có thể bỏ qua giá trị mới; các khối cấu hình JSON được thay nguyên khối nên có thể mất trường do máy chủ bổ sung.
- YouTube: [upstream Maasea](https://github.com/Maasea/sgmodule) kiểm thử cho Surge; chưa xác nhận chạy trên Shadowrocket/iPhone thực tế.
- Các script tải từ nhánh `main`/`master` có thể được tác giả cập nhật sau này.
- Script Locket hiện có số điện thoại trong popup; bản ghép không chỉnh sửa nội dung script.

## Cấu trúc repo

```text
Locket_Only_60s_Full/
├── README.md
├── SHA256SUMS.txt
├── module/
│   ├── locket-only-60s-full.module
│   └── locket-60s-youtube-huyhoang.module
└── scripts/
    ├── forceGold4.3_60s_full.js
    ├── header7_60s_full.js
    └── locketfix8_60s_full.js
```

`SHA256SUMS.txt` kiểm tra các file trong thư mục này; không bao gồm script YouTube tải từ upstream.
