# HA Tiles — Home Assistant kiểu Windows Phone 10 (Android 7+)

Ứng dụng Android bình thường (không phải launcher) hiển thị thiết bị Home Assistant
dưới dạng các ô (tile) phẳng như màn hình Start của Windows Phone 10.

## Tính năng
- Ô Nhỏ (1x1) / Vừa (2x2) / Rộng (4x2) / Lớn (4x4), bấm giữ vào ô để đổi.
- Chỉnh kích thước ô, khoảng cách, độ trong suốt, màu chủ đạo, màu riêng từng ô.
- Đặt ảnh nền từ thư viện ảnh, chỉnh độ tối của ảnh nền.
- Bấm ô để bật/tắt đèn, công tắc, quạt, rèm, khoá, chạy scene/script...
- Tự cập nhật trạng thái theo chu kỳ (mặc định 5 giây).
- Chạy trên Android 7.0 trở lên, không dùng thư viện ngoài.

## Build APK bằng GitHub (không cần Android Studio)
1. Tạo repository mới trên github.com (để Private cũng được).
2. Tải toàn bộ nội dung thư mục này lên (Add file > Upload files, kéo cả thư mục `.github` và `app`).
   Nếu `.github/workflows/build.yml` không lên, tạo thủ công: Add file > Create new file,
   gõ tên `.github/workflows/build.yml` rồi dán nội dung file đó vào.
3. Vào tab **Actions**, chọn "Build APK" > **Run workflow** (hoặc nó tự chạy sau mỗi lần upload).
4. Đợi khoảng 3-6 phút. Mở lần chạy xong (dấu tích xanh) > cuộn xuống **Artifacts** > tải `HATiles-apk`.
5. Giải nén file zip được `app-debug.apk`, chép vào máy, cài đặt
   (cho phép "cài ứng dụng từ nguồn không xác định" nếu máy hỏi).

## Dùng
1. Mở app, vào Cài đặt: nhập địa chỉ HA (vd `192.168.1.10:8123`) và Long-lived access token
   (Hồ sơ HA > Bảo mật > Mã truy cập có thời hạn dài > Tạo mã). Bấm "Lưu và kiểm tra kết nối".
2. Quay lại, bấm dấu **+** để chọn thiết bị cần hiện.
3. Bấm giữ ô để đổi tên, kích thước, màu, di chuyển, xoá.

## Ghi chú
- Biểu tượng ô là emoji của hệ thống; máy quá cũ có thể hiện ô vuông ở một vài biểu tượng.
- Android 7 cần Android System WebView không còn dùng, nhưng cần TLS 1.2: ổn.
  Riêng Android 7.0 (không phải 7.1.1) không tin chứng chỉ Let's Encrypt mới (ISRG Root X1):
  nếu dùng HTTPS Let's Encrypt mà báo lỗi SSL, hãy dùng địa chỉ http trong LAN hoặc bật tuỳ chọn chấp nhận chứng chỉ.
