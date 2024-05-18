# Máy đọc thẻ RFID với Arduino

## Mô tả
Dự án này sử dụng Arduino Uno, mô-đun RFID, LCD I2C và 3 nút ấn để tạo ra một hệ thống quản lý thẻ RFID. Hệ thống cho phép thêm, xóa các thẻ RFID vào bộ nhớ EEPROM của Arduino và sử dụng một thẻ chính (master) để truy cập vào menu chính.

## Linh kiện
- Arduino Uno
- RFID module
- LCD I2C
- 3 nút ấn

## Cách hoạt động
### Menu đa cấp
Hệ thống bao gồm các chức năng:
- **Back**: Quay lại menu trước đó.
- **Thêm thẻ**: Thêm thẻ RFID mới vào hệ thống.
- **Xóa thẻ bất kỳ**: Xóa một thẻ RFID cụ thể.
- **Xóa tất cả thẻ**: Xóa toàn bộ thẻ RFID khỏi hệ thống.

### Các nút điều khiển
- **Nút 1 (Chọn)**: Chọn menu hoặc xác nhận thao tác.
- **Nút 2 (Lên)**: Di chuyển lên trong menu.
- **Nút 3 (Xuống)**: Di chuyển xuống trong menu.

### Hoạt động của hệ thống
- Sau khi quét thẻ chính (master), hệ thống sẽ vào menu chính.
- Trong menu chính, người dùng có thể thêm hoặc xóa các thẻ thành phần.
- Bộ nhớ EEPROM của Arduino được sử dụng để lưu UID của các thẻ RFID.

### Thẻ RFID
- Thẻ chính (master): UID: `99 55 58 251`
- Thẻ phụ (slave):
  - UID: `35 4103 53`
  - UID: `1790607 251`

## Hướng dẫn sử dụng
1. Quét thẻ chính để vào menu.
2. Sử dụng nút 2 (Lên) và nút 3 (Xuống) để di chuyển qua các tùy chọn menu.
3. Sử dụng nút 1 (Chọn) để xác nhận lựa chọn hoặc quay lại menu trước đó.
4. Để thêm thẻ, chọn "Thêm thẻ" và quét thẻ mới.
5. Để xóa thẻ, chọn "Xóa thẻ bất kỳ" và quét thẻ cần xóa.
6. Để xóa tất cả thẻ, chọn "Xóa tất cả thẻ".

## Video Demo
[Video hướng dẫn](https://www.youtube.com/watch?v=lwaJDORCzVM)

## Mã nguồn
Tất cả mã nguồn và tài liệu liên quan có thể được tìm thấy trong repository này.


