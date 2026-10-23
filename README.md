# bocthamhoithao – Bốc thăm chia bảng thể thao HPDQ 2026

## Tính năng
- 22 đội, 2 môn: Bóng chuyền hơi và Kéo co; kết quả mỗi môn độc lập.
- Phân bổ đội thủ công theo kết quả bốc thăm trực tiếp.
- 8 bảng/môn: A–F tối đa 3 đội; G–H tối đa 2 đội.
- Xuất bảng kết quả Excel-compatible `.xls`.
- Lưu tạm trên trình duyệt; khi điền cấu hình Firebase, dữ liệu đồng bộ qua Cloud Firestore.

## Cấu hình Firebase
1. Vào Firebase Console, chọn dự án `hpdq-training` hoặc tạo dự án riêng cho giải.
2. Tạo Web App trong Project settings > Your apps.
3. Sao chép Firebase web config vào `firebase-config.js` (không đặt service account/private key ở đây).
4. Tạo Cloud Firestore database.
5. Dán nội dung `firestore.rules` vào Firestore Rules để thử nghiệm nội bộ.
6. Lưu và tải lại website. Thanh trạng thái góc trên báo `Đã kết nối Firebase` khi kết nối được.

**Cảnh báo:** Quy tắc Firestore hiện là prototype mở đọc/ghi để kiểm thử nhanh. Không dùng cho dữ liệu công khai hoặc nhạy cảm. Trước khi công bố rộng, cần bật Firebase Authentication và giới hạn quyền ghi cho tài khoản quản trị.

## Đưa lên GitHub và Render
1. Tạo repository GitHub mới, ví dụ `bocthamhoithao`.
2. Upload toàn bộ các file trong thư mục này lên root repository.
3. Trên Render chọn New > Static Site, kết nối repository.
4. Build command để trống; Publish directory đặt `.` (root). Có thể dùng `render.yaml`.
5. Mỗi lần push commit lên nhánh triển khai, Render tự deploy lại.

## Lưu ý
Cấu hình Firebase Web App là thông tin client được thiết kế để xuất hiện trên trình duyệt. Bảo vệ dữ liệu bằng Firestore Security Rules và Authentication, không dựa vào việc giấu `apiKey`.
