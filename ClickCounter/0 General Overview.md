<div style="display: flex;">

<div style="flex: 50%; padding: 10px; border: 01px">

# 0. General Overview

ClickCounter system consists of:

1. ESP32 modules with attached switch buttons. It is connected to a local network via WiFi and sends TCP/IP messages on each click of the button.
2. A Windows computer running a service (daemon) app. It receives TCP/IP messages from the ESP32 modules and saves them.

Actual processing of the stored data and the generation of the report is done by ClickTally, another service running on Windows.

Windows installation of ClickCounter is a straightforward setup of Windows for TCP/IP connection and command-line execution of Windows service creation.

Since ClickCounter is written as a service, it runs silently in the background without a user interface until it is manually stopped.

And it is configured to start automatically when the computer turns on.  There is no need to separately run the process after the computer has been turned off.

ESP32 installation requires a USB connection from Windows to ESP32 module via Arduino IDE and the modification of ESP32 code to specify the computer name, network ID/password.

</div>

<div style="flex: 50%; padding: 10px; border: 0px">

# 0. Tổng quan chung

Hệ thống ClickCounter bao gồm:

1. Thiết bị ESP32 có gắn nút chuyển đổi. Chúng được kết nối với mạng cục bộ qua WiFi và gửi tin nhắn TCP/IP sau mỗi lần nhấp vào nút.
2. Một máy tính Windows chạy ứng dụng dịch vụ (daemon). Nó nhận tin nhắn TCP/IP từ mô-đun ESP32 và lưu trữ chúng.

Việc xử lý thực tế dữ liệu được lưu trữ và tạo báo cáo được thực hiện bởi ClickTally, một dịch vụ khác chạy trên Windows.

Cài đặt Windows của ClickCounter là một thiết lập Windows đơn giản để kết nối TCP/IP và thực thi dòng lệnh tạo ra một dịch vụ Windows.

Vì ClickCounter được viết dưới dạng dịch vụ nên nó chạy âm thầm trong nền mà không có giao diện người dùng cho đến khi dừng thủ công.

Và nó được cấu hình để tự động khởi động khi máy tính bật. Không cần phải chạy một quy trình riêng sau khi tắt máy tính.

Việc cài đặt ESP32 yêu cầu kết nối USB từ Windows đến ESP32 thông qua Arduino IDE. Và việc sửa đổi mã ESP32 để chỉ định tên máy tính, ID/mật khẩu mạng.
</div>
</div>

