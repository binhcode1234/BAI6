# STM32F103C8T6 + DS3231 RTC + UART (SPL Library)

## 📌 Giới thiệu
Dự án này sử dụng **STM32F103C8T6 (Blue Pill)** để giao tiếp với module **DS3231 RTC** qua giao thức **I2C**, sau đó gửi dữ liệu thời gian thực (giờ:phút:giây) ra **UART** để hiển thị trên terminal (UART baudrate = 9600).

- Thư viện sử dụng: **Standard Peripheral Library (SPL)**
- Vi điều khiển: **STM32F103C8T6**
- RTC: **DS3231**
- Giao tiếp: **I2C1 (PB6 - SCL, PB7 - SDA)**, **USART1 (PA9 - TX, PA10 - RX)**

---

## ⚙️ Chức năng chính
- Khởi tạo I2C1 để giao tiếp với DS3231.  
- Khởi tạo UART1 để truyền dữ liệu ra máy tính.  
- Đọc thời gian thực từ DS3231 (giờ, phút, giây).  
- Gửi chuỗi thời gian qua UART để hiển thị trên terminal.  
- Hỗ trợ set lại thời gian cho DS3231 (chỉ dùng khi cần).  

---

## 🖥️ Cấu hình phần cứng

### Kết nối STM32 ↔ DS3231
| STM32F103C8T6 | DS3231 |
|---------------|--------|
| PB6 (I2C1_SCL) | SCL    |
| PB7 (I2C1_SDA) | SDA    |
| 3.3V          | VCC    |
| GND           | GND    |

### Kết nối STM32 ↔ UART (USB-TTL / ST-LINK VCP)
| STM32F103C8T6 | USB-TTL |
|---------------|---------|
| PA9 (USART1_TX)  | RX      |
| PA10 (USART1_RX) | TX      |
| GND              | GND     |

---

## 🛠️ Hướng dẫn sử dụng
1. Clone repo về:
   ```bash
   git clone https://github.com/your-username/stm32-ds3231-uart.git
