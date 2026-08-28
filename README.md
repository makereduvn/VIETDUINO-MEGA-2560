# Vietduino Mega 2560 (Arduino Mega 2560 Compatible)

## Giới thiệu
**Vietduino Mega 2560** là bo mạch phát triển do MakerEDU nghiên cứu và sản xuất, dựa trên nguyên mẫu Arduino Mega 2560, được nâng cấp toàn diện về phần cứng, hướng tới độ ổn định cao, hiệu suất tốt và độ bền lâu dài – đặc biệt phù hợp cho Giáo Dục STEM, Phòng Thí Nghiệm, Maker Space, nghiên cứu và phát triển ứng dụng nhúng cơ bản.

**Vietduino Mega 2560** được thiết kế tương thích hoàn toàn với Arduino Mega 2560 về hình dạng, chuẩn chân tín hiệu và cách sử dụng, cho phép người dùng tận dụng trực tiếp toàn bộ hệ sinh thái Arduino: thư viện, ví dụ mẫu, shield và cộng đồng hỗ trợ.

## Ưu điểm nổi bật
- Tương thích hoàn toàn Arduino Mega 2560, giữ nguyên form factor, vị trí chân và chuẩn giao tiếp.
- Nâng cấp mạch nguồn xung giảm áp hiệu suất chuyển đổi cao, tỏa nhiệt thấp, tiết kiệm năng lượng.
- Sử dụng IC chuyển đổi USB–UART chính hãng CH343P, đảm bảo giao tiếp ổn định, nạp chương trình tin cậy và độ bền cao khi sử dụng lâu dài.
- Bảo vệ cổng USB máy tính với chức năng tự động cách ly nguồn USB khi cấp nguồn ngoài qua chân VIN hoặc Jack DC, giúp tăng độ an toàn trong quá trình học tập và thử nghiệm.

## Thông số kỹ thuật

### Thông tin chung
- Model: Vietduino Mega 2560 (Arduino Mega 2560 Compatible)
- Vi điều khiển: ATmega2560-16AU (Microchip)
- Điện áp hoạt động: 5VDC
- Điện áp đầu vào VIN: 6 ~ 24VDC
- Clock Speed: 16 MHz

### Bộ nhớ
- Flash Memory: 256 KB (8 KB sử dụng cho Bootloader)
- SRAM: 8 KB
- EEPROM: 4 KB

### Dòng điện
- Dòng DC mỗi chân I/O: Tối đa 20 mA
- Dòng DC chân 3V3: Tối đa 700 mA
- Dòng DC chân 5V: Tối đa 1500 mA

### Giao tiếp & nạp chương trình
- IC USB–UART: CH343P
- Cổng kết nối máy tính: USB-C

### Các chân tín hiệu
- Digital I/O: 54 chân
- PWM: 15 chân
- Analog Input: 16 chân
- LED_BUILTIN: Chân 13

![Vietduino Mega 2560](/extras/VietduinoMega2560_0.png)

### Kích thước
![Vietduino Mega 2560](/extras/VietduinoMega2560_2.jpg)

## Hướng dẫn sử dụng cơ bản với Arduino IDE

### Bước 1: Cài đặt Arduino IDE
- Tải và cài đặt [Phần mềm Arduino IDE từ trang chủ Arduino](https://www.arduino.cc/en/software) phù hợp với hệ điều hành đang sử dụng.

### Bước 2: Kết nối mạch với máy tính
- Kết nối Vietduino Mega 2560 với máy tính bằng cáp USB-C.
- Khi kết nối thành công, LED nguồn (ON) trên mạch sẽ sáng.

### Bước 3: Cài đặt driver CH340
- Vietduino Uno sử dụng IC CH340 để giao tiếp USB–UART.
- Thông thường Driver sẽ tự nhận trên hầu hết các hệ điều hành, nếu máy tính chưa nhận driver, [tải và cài đặt Driver CH343P tại đây.](https://www.wch-ic.com/downloads/CH341SER_ZIP.html)

### Bước 4: Cấu hình mạch trong Arduino IDE
Thực hiện các thiết lập sau trong Arduino IDE:
- Chọn loại board: Tools → Board → Arduino AVR Boards → **Arduino Mega or Mega 2560**
- Chọn Processor: **ATmega2560 (Mega 2560)**
- Chọn cổng kết nối (Port): Tools → Port → chọn cổng tương ứng với Vietduino Mega 2560 (nếu chưa xác định được, hãy rút cáp USB và cắm lại để nhận diện cổng mới xuất hiện)

![Vietduino Mega 2560](/extras/VietduinoMega2560_3.jpg)

### Bước 5: Nạp chương trình thử nghiệm (Blink)
Sau khi cấu hình xong, bạn có thể nạp chương trình Blink để kiểm tra mạch.
Chương trình này sẽ làm LED_BUILTIN tại chân D13 chớp tắt mỗi 1 giây.
```ino
/*
  Blink
  Turns an LED_BUILTIN on D13 of Vietduino Mega 2560 for one second, then off for one second, repeatedly.
*/
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN on D13 as an output.
  pinMode(13, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(13, HIGH);  // turn the LED on (HIGH is the voltage level)
  delay(1000);                      // wait for a second
  digitalWrite(13, LOW);   // turn the LED off by making the voltage LOW
  delay(1000);                      // wait for a second
}
```
![Vietduino Mega 2560](/extras/VietduinoMega2560_4.jpg)

## Lưu ý sử dụng an toàn
- Không đặt mạch trên bề mặt kim loại dẫn điện
- Tránh môi trường:
  - Ẩm ướt
  - Nhiệt độ cao
  - Nhiều bụi dẫn điện
- Nên sử dụng với nguồn điện chất lượng tốt
- Luôn đảm bảo mạch:
  - Không bị chập mạch
  - Không đấu sai cực nguồn
- Nên ngắt nguồn ngoài trước khi thay đổi đấu nối phần cứng.

## Hình ảnh sản phẩm
![Vietduino Mega 2560](/extras/VietduinoMega2560_5.png)
![Vietduino Mega 2560](/extras/VietduinoMega2560_6.png)

## Miễn trừ trách nhiệm
Sản phẩm này là bo mạch phát triển được thiết kế phục vụ cho mục đích nghiên cứu, thử nghiệm và học tập, không phải là một thiết bị hoàn chỉnh. Trong trường hợp người dùng kết hợp mạch này với các linh kiện, thiết bị hoặc phần mềm khác để tạo thành một hệ thống hoặc sản phẩm hoàn chỉnh, mọi chức năng và tính phù hợp của sản phẩm sau cùng đều thuộc trách nhiệm của người dùng.
