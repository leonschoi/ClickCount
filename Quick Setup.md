<table style="border-style: none">
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

# Quick Setup

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

This is the setup procedure for the already installed system. For complete installation steps, see the Installation section of the 4 component chapters.

</td>
<td valign="top" width="50%" style="border-style: none">

Đây là quy trình thiết lập cho hệ thống đã cài đặt. Để biết các bước cài đặt hoàn chỉnh ngay từ đầu, hãy xem phần cài đặt của 4 chương thành phần.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## Windows

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Once all the installation files are copied to the target directory and IIS is configured, the ClickCounter System can be brought up or down quickly as follows:

</td>
<td valign="top" width="50%" style="border-style: none">

Khi tất cả các tệp cài đặt được sao chép vào thư mục đích và IIS được định cấu hình, ClickCounter System có thể được đưa lên hoặc xuống nhanh chóng như sau:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

### Web Server

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Go to the `Internet Information Services (IIS) Manager` app (type `IIS` in the taskbar search box)

</td>
<td valign="top" width="50%" style="border-style: none">

- Vào ứng dụng `Internet Information Services (IIS) Manager` (gõ `IIS` vào ô tìm kiếm trên taskbar)

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/3474b66e-9c66-4c89-9a90-79b40c8d96d8" alt="IIS Start" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- On the left pane of `Internet Information Services (IIS) Manager`, expand `"Hostname" (Hostname\User)` > `Sites`

</td>
<td valign="top" width="50%" style="border-style: none">

- Trong khung bên trái của `Internet Information Services (IIS) Manager`, mở rộng `"Hostname" (Hostname\User)` > `Sites`
</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/ca683859-79d6-42a2-8e5e-3f629a234a01" alt="IIS Manager" width="700"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Click on the `ClickCounter` site.  The `Actions` pane opens on the right side.
- In the `Manage Website` section, choose `Start` or `Stop`.

</td>
<td valign="top" width="50%" style="border-style: none">

- Bấm vào trang `ClickCounter`. Khung `Actions` mở ra ở phía bên phải.
- Trong phần `Manage Website` chọn `Start` hoặc `Stop`.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

### ClickCounter and ClickTally Services

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Go to the `Administrator: Command Prompt` window (type `cmd` in the taskbar search box, right click on the `Command Prompt App`, select `Run as administrator`)

</td>
<td valign="top" width="50%" style="border-style: none">

- Vào cửa sổ `Administrator: Command Prompt` (gõ `cmd` vào hộp tìm kiếm trên thanh tác vụ, nhấp chuột phải vào `Command Prompt App`, chọn `Run as administrator`)

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/9cef7aa1-f8c9-411e-95ce-c8e10740c7d0" alt="CMD Start" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- In the prompt window, run `sc.exe start "ClickCounter"`

</td>
<td valign="top" width="50%" style="border-style: none">

- Trong prompt window, chạy `sc.exe start "ClickCounter"`

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/650e00c7-7ae8-4f27-9384-cd05698ac8dd" alt="CMD Prompt" width="800"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Two cases are shown: if the service `ClickCounter` was not running, and if it was already running.
- Also shown are the two cases for `sc.exe stop "ClickCounter"` to stop the service.

</td>
<td valign="top" width="50%" style="border-style: none">

- Hai trường hợp được hiển thị: nếu service `ClickCounter` không chạy và nếu nó đã chạy.
- Cũng hiển thị hai trường hợp `sc.exe stop "ClickCounter"`  để dừng service.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Run `ClickTally` by executing `sc.exe start "ClickTally"`. The response will be the same as `ClickCounter`.

</td>
<td valign="top" width="50%" style="border-style: none">

- Chạy `ClickTally` bằng cách thực thi `sc.exe start "ClickTally"`. Phản hồi sẽ giống như `ClickCounter`.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

### Load Template Excel Files

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

In the Windows Explorer of any computer on the local network shared by the computer `"Hostname"`, type `\\"Hostname"` to view the contents of accesible directories

</td>
<td valign="top" width="50%" style="border-style: none">

Trong Windows Explorer của bất kỳ máy tính nào trên mạng cục bộ được chia sẻ bởi máy tính `"Hostname"`, hãy nhập `\\"Hostname"` để xem nội dung của các thư mục có thể truy cập
</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/b341e510-56f3-4eec-9394-84b7aa3edf35" alt="Hostname" width="700"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Click on `ClickTemplate` or type to complete `\\"Hostname"\ClickTemplate` then `Enter`.
</td>
<td valign="top" width="50%" style="border-style: none">

Nhấp vào `ClickTemplate` hoặc nhập để hoàn thành `\\"Hostname"\ClickTemplate` rồi `Enter`.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/e8801590-321c-4670-9fac-d07d049dcb22" alt="ClickTemplate" width="700"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Copy the template Excel files to this directory for processing by `ClickTally`.  A file can be added or deleted any time. When a file is added, `ClickTally` immediately converts it to a report HTML file and include it in the ongoing process.  When a file is deleted, the corresponding report HTML file will remain but it will not be included in the further process.  

</td>
<td valign="top" width="50%" style="border-style: none">

Sao chép tệp template Excel vào thư mục này để `ClickTally` xử lý. Một tập tin có thể được thêm hoặc xóa bất cứ lúc nào. Khi một tệp được thêm vào, `ClickTally` ngay lập tức chuyển đổi tệp đó thành tệp HTML báo cáo và đưa tệp đó vào quy trình đang diễn ra. Khi một tệp bị xóa, tệp HTML báo cáo tương ứng sẽ vẫn còn nhưng nó sẽ không được đưa vào quy trình tiếp theo.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

## ESP32

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

After installing the Arduino IDE and necessary libraries, the C++ code can be modified to connect to the ClickCounter TCP listener.

</td>
<td valign="top" width="50%" style="border-style: none">

Sau khi cài đặt Arduino IDE và các thư viện cần thiết, mã C++ có thể được sửa đổi để kết nối với ClickCounter TCP listener.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Connect the computer `"Hostname"` to the ESP32 board using a micro USB cable. In Windows Explorer, go to the directory `C:\YIC\ESP32_click_counter\`:

</td>
<td valign="top" width="50%" style="border-style: none">

Kết nối máy tính `"Hostname"` với ESP32_board bằng cáp micro USB. Trong Windows Explorer, đi tới thư mục `C:\YIC\ESP32_click_counter\`:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/48faf241-d25c-4b95-847e-3e932763358e" alt="ESP32_click_counter" width="700"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Double click on the `ESP32_click_counter.ino` file to bring up Arduino IDE.  Select `config.cpp`

</td>
<td valign="top" width="50%" style="border-style: none">

Nhấp đúp chuột vào tệp `ESP32_click_counter.ino` để hiển thị Arduino IDE. Chọn `config.cpp`
</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/1c8deff4-7414-40d6-8f7e-453f526cd8a1" alt="config.cpp" width="800"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The `HostInfo` type is used to declare a variable containing the host computer name and port number. Using `DESKTOP-0AJUHED` as the server name, set:

</td>
<td valign="top" width="50%" style="border-style: none">

Loại `HostInfo` được sử dụng để khai báo một biến chứa tên máy tính chủ và số port. Sử dụng `DESKTOP-0AJUHED` làm tên máy chủ, đặt:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

```C++
//
// Host computer name and port number
//
HostInfo host1("DESKTOP-0AJUHED", PORT_NUMBER);
```

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The `LoginInfo` array contains a list of Wi-Fi loginID/password and host computer in the network. Set the `ssid` and `password` of the local Wi-Fi network:

</td>
<td valign="top" width="50%" style="border-style: none">

Mảng `LoginInfo` chứa danh sách Wi-Fi loginID/password và máy chủ trong mạng. Đặt `ssid` và `password` của mạng Wi-Fi cục bộ:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

```C++
//
// WiFi login/pw and ClickCounter host to connect on the network
//
LoginInfo loginInfoStore[MAX_LOGIN_INFO_SIZE] {
  // ssid        password               host
  {"YIC Office", "enter password here", &host1}
};
```

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Now click on the `config.h` tab:

</td>
<td valign="top" width="50%" style="border-style: none">

Bây giờ hãy nhấp vào tab `config.h`:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/1fa9bfa3-3547-4731-8b41-b36b9cb26793" alt="config.h" width="800"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- `pinNumberButton` is the pin number that the button switch is connected to
- `PORT_NUMBER` is 8201 for ClickCounter service.
- `MAX_LOGIN_INFO_SIZE` is used to specify the number of Wi-Fi loginID/password list entries in `config.cpp`. In this case, `=1` because there is only one entry:

</td>
<td valign="top" width="50%" style="border-style: none">

- `pinNumberButton` là số chân mà công tắc nút được kết nối với
- `PORT_NUMBER` là 8201 cho ClickCounter service.
- `MAX_LOGIN_INFO_SIZE` được sử dụng để chỉ định số lượng mục danh sách Wi-Fi loginID/password trong `config.cpp`. Trong trường hợp này, `=1` vì chỉ có một mục:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

```C++
//
// Wi-Fi and host PC info variables
//
const int PORT_NUMBER = 8201; 
const int MAX_LOGIN_INFO_SIZE = 1;
```

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

When the program runs in the ESP32, it will goes through the Wi-Fi `ssid`/`password` list in order and tries to connect each for 20 seconds.  Once it connects to a network, it will switch to button click sending mode.

The following items in Arduino IDE must be set before running the program. They tend to be unselected when the environment changes, hence need to be checked often.

</td>
<td valign="top" width="50%" style="border-style: none">

Khi chương trình chạy trong ESP32, nó sẽ đi qua danh sách Wi-Fi `ssid`/`password` theo thứ tự và cố gắng kết nối với từng danh sách trong 20 giây. Sau khi kết nối mạng sẽ chuyển sang chế độ gửi nút nhấn.

Các mục sau trong Arduino IDE phải được đặt trước khi chạy chương trình. Chúng có xu hướng không ổn định khi môi trường thay đổi nên cần được kiểm tra thường xuyên.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

Board selection:\
Tools > Board > esp32 > ESP32 Dev Module

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/e4bc7f77-f921-44e2-bbd0-b8a4c37760b0" alt="ESP32 Board" width="800"/>  

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

COM port selection:\
Tools > Port > COM#\

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/38a0f185-f2ea-4a15-bb15-68f4e624288f" alt="ESP32 Port" width="800"/>  

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

Serial Monitor window toggle:\
Tools > Serial Monitor (Ctrl-Shift-M), or click on the right magnifying glass icon.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

On the right side of the Serial Monitor window:\
Set COM baud rate to 115200 baud

</td>
<td valign="top" width="50%" style="border-style: none">

Ở bên phải cửa sổ Serial Monitor:\
Đặt COM baud rate thành 115200 baud

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/2269de6d-1d80-426d-ba8b-63ef94c5a4ff" alt="Serial Monitor" width="800"/>  

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Compile the program in one of two ways:

</td>
<td valign="top" width="50%" style="border-style: none">

Biên dịch chương trình theo một trong hai cách:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

1. On the menu:\
   Sketch > Verify/Compile (Ctrl-R)
2. On the top toolbar, click on the first button showing the check sign.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Compilation messages are displayed on the `Output` window.

Compile and upload the program in one of two ways:

</td>
<td valign="top" width="50%" style="border-style: none">

Thông báo biên dịch được hiển thị trên cửa sổ `Output`.

Biên dịch và tải chương trình lên theo một trong hai cách:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

1. On the menu:\
   Sketch > Upload (Ctrl-U)
2. On the top toolbar, click on the second button showing the right arrow.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Now the ESP32 board is running and the interactive messages will display on the Serial Monitor window.

</td>
<td valign="top" width="50%" style="border-style: none">

Bây giờ ESP32 board đang chạy và các thông báo tương tác sẽ hiển thị trên cửa sổ Serial Monitor.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/0bb327d0-9aa4-4ed3-98f6-883c3b9ac78f" alt="ESP32 Run" width="800"/>  

</td>
</tr>
</table>
