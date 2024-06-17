# Máy đọc thẻ RFID với Arduino

## Mô tả
Dự án này sử dụng Arduino Uno, mô-đun RFID, LCD I2C và 3 nút ấn để tạo ra một hệ thống quản lý thẻ RFID. Hệ thống cho phép thêm, xóa các thẻ RFID vào bộ nhớ EEPROM của Arduino và sử dụng một thẻ chính (master) để truy cập vào menu chính.

## Linh kiện
- Arduino Uno. Link mua sp: https://banlinhkien.com/kit-arduino-uno-r3-atmega16u2-p6649361.html
- RFID module. Link mua sp: https://shopee.vn/product/310609561/5556546486?gad_source=1&gclid=Cj0KCQjwvb-zBhCmARIsAAfUI2tgg7-2gpE3SnYO4SnvqMnn6QeFs5iUURIvxFL_U16uilpsNGNkUaAaAhieEALw_wcB
- LCD I2C. Link mua sp: https://nshopvn.com/product/lcd-1602-kem-module-i2c/?variant=117000&gad_source=1&gclid=Cj0KCQjwvb-zBhCmARIsAAfUI2uy6hofBDiI8MhrMTGIfjDDgzsIsVwzwOjqIQ43kNSC4gR9H5KtMFMaAjPAEALw_wcB
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
## Sơ đồ nguyên lý
![image](https://github.com/betosan2810/may_Doc_the/assets/147693423/9efd742d-593b-421f-a0b9-7db3403955ef)

## Thiết kế phần mềm
### Xác định trạng thái nút bấm
- Các nút bấm lên, xuống và menu được đọc trạng thái thông qua các cổng GPIO và sử dụng cơ chế ngắt để phát hiện thay đổi trạng thái.
### Điều khiển màn hình LCD
- Màn hình LCD I2C được điều khiển để hiển thị các thông báo và hướng dẫn cho người dùng.
Ví dụ: Hiển thị thông báo chào mừng và yêu cầu người dùng nhập thẻ:
![image](https://github.com/betosan2810/may_Doc_the/assets/147693423/2ca4c243-eb27-4bab-959f-e28d4897d886)
### Đọc và ghi EEPROM
- Bộ nhớ EEPROM được dùng để lưu trữ và quản lý danh sách thẻ RFID
- Cơ chế đọc và ghi của EEPROM:
  - Ô đầu tiên lưu trữ số lượng thẻ đã lưu
  - 4 ô từ 1-4 chứa ID thẻ chủ 
  - Các ô tiếp theo (4 ô 1 nhóm) để ghi ID từ các thẻ RFID
![image](https://github.com/betosan2810/may_Doc_the/assets/147693423/55e6c236-c12a-4e6f-9e85-250b8dde3d93)
   

        

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


