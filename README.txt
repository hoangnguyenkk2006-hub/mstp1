# Food Dryer PWA – giao diện điện thoại

## Nội dung
- `index.html`: giao diện điện thoại tối ưu cảm ứng.
- `manifest.webmanifest`: khai báo ứng dụng PWA.
- `sw.js`: lưu bộ khung giao diện để mở lại khi offline.
- `icon.svg`: biểu tượng ứng dụng.

## Chạy thử trên PC
1. Giải nén thư mục.
2. Mở Terminal tại thư mục này.
3. Chạy máy chủ web tĩnh, ví dụ:
   `python -m http.server 8000`
4. Mở `http://localhost:8000`.

## Truy cập từ điện thoại trong mạng LAN
- PC và điện thoại phải cùng mạng nội bộ.
- Lấy địa chỉ IPv4 của PC bằng `ipconfig`.
- Trên điện thoại mở `http://DIA_CHI_IP_CUA_PC:8000`.

## Lưu ý quan trọng về cài đặt PWA
Service Worker và cài đặt PWA trên trình duyệt điện thoại thường yêu cầu HTTPS. `localhost` được xem là ngữ cảnh an toàn trên chính PC, nhưng địa chỉ LAN dạng `http://192.168.x.x` thường không được xem là ngữ cảnh an toàn. Vì vậy, bản này có đầy đủ các tệp PWA, nhưng để cài đặt ổn định trên điện thoại cần phục vụ qua HTTPS trong mạng nội bộ (hoặc dùng giải pháp triển khai HTTPS phù hợp).

## Trạng thái chức năng
Đây là giao diện tĩnh, không có dữ liệu giả lập. Các nút và ô nhập đang bị khóa có chủ ý. Chưa có API, chưa có bản đồ thanh ghi Modbus và chưa gửi lệnh đến thiết bị. Khi có phần cứng và tài liệu Modbus của từng Slave, mới bổ sung backend Python/Flask và mở khóa các chức năng đã kiểm thử.

Service Worker chỉ lưu giao diện. Khi PC hoặc mạng nội bộ đến PC mất kết nối, ứng dụng có thể mở phần giao diện đã lưu nhưng không thể đọc cảm biến hay điều khiển thiết bị.
