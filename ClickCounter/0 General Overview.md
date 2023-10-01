<table style="border-style: none">
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

# 0. General Overview

ClickCounter system consists of:

1. ESP32 modules with attached switch buttons. It is connected to the local network via WiFi and sends TCP/IP messages on each click of the button.
2. A Windows computer running a service (daemon) app. It receives TCP/IP messages from the ESP32 modules and saves them.

The actual processing of stored data and report generation is done by ClickTally, another service running on Windows.

Windows installation of ClickCounter is a straightforward setup of Windows for TCP/IP connection and command-line execution of Windows service creation.

Since ClickCounter is written as a service, it runs silently in the background without a user interface until it is manually stopped.

And it is configured to start automatically when the computer turns on.  There is no need to separately run the process after the computer has been turned off.

ESP32 installation requires a USB connection from Windows to ESP32 module via Arduino IDE and the modification of ESP32 code to specify the computer name, network ID/password.

</td>
<td valign="top" width="50%" style="border-style: none">

# 0. Tổng quan chung

Hệ thống ClickCounter bao gồm:

1. Mô-đun ESP32 có gắn công tắc. Nó được kết nối với mạng cục bộ qua WiFi và gửi tin nhắn TCP/IP mỗi lần nhấp vào nút.
2. Máy tính Windows chạy các ứng dụng service (daemon). Nó nhận tin nhắn TCP/IP từ các mô-đun ESP32 và lưu trữ chúng.

Việc xử lý thực tế dữ liệu được lưu trữ và tạo báo cáo được thực hiện bởi ClickTally, một service khác chạy trên Windows.

Quá trình cài đặt Windows của ClickCounter là một thiết lập Windows đơn giản để kết nối TCP/IP và thực thi dòng lệnh tạo ra tệp service.

Vì ClickCounter được viết dưới dạng service nên nó chạy âm thầm trong nền mà không có giao diện người dùng cho đến khi dừng thủ công.

Và nó được cấu hình để tự động khởi động khi máy tính bật. Không cần phải chạy một quy trình riêng sau khi tắt máy tính.

Việc cài đặt ESP32 yêu cầu kết nối USB từ mô-đun Windows đến ESP32 thông qua Arduino IDE và sửa đổi mã ESP32 để chỉ định tên máy tính, ID/mật khẩu mạng.

</td>
</tr>
</table>
