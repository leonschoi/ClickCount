<table style="border-style: none" >
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

# 5. ESP32_click_counter User Guide

</td>
<td valign="top" width="50%" style="border-style: none">

# 5. Hướng dẫn sử dụng ESP32_click_counter

</td>
</tr>

<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none"></td>
<td valign="top" width="50%" style="border-style: none"></td>
</tr>

<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

## 5.1. C++ variables setting

The ESP32 is used for two tasks

1. Detect switch button press
2. Transmit the press signal to ClickCounter computer

The C++ program variables used by these two tasks are in two files: `config.cpp` and `config.h`.

### Switch button press

For switch button press detection, we need to specify the pin connected to the switch.  It is in `config.h`

```C++
//
// ESO32 pin connection variable
//
const uint8_t pinNumberButton = 27; // pin ID the switch is connected to
```

</td>
<td valign="top" width="50%" style="border-style: none">


## 5.1. Đặt biến C++

ESP32 được sử dụng cho hai nhiệm vụ

1. Phát hiện nút chuyển đổi nhấn
2. Truyền tín hiệu báo chí tới máy tính ClickCounter

Các biến chương trình C++ được hai tác vụ này sử dụng nằm trong hai tệp: `config.cpp` và `config.h`.

### Nhấn nút chuyển đổi

Để phát hiện việc nhấn nút công tắc, chúng ta cần chỉ định chân kết nối với công tắc. Nó nằm trong `config.h`

```C++
//
// ESO32 pin connection variable
//
const uint8_t pinNumberButton = 27; // pin ID the switch is connected to
```

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

### Signal transmission

To transmit signal to ClickCounter computer, we need WiFi loginID/password and the host computer name/port.

In `config.h`, two constants are defined.

- `PORT_NUMBER` is the same for all ClickCounter for now.
- `MAX_LOGIN_INFO_SIZE` is used to specify WiFi loginID/password list entry count.

```C++
//
// WiFi and host PC info variables
//
const int PORT_NUMBER = 8201;      // port number used for ClickCount service on Windows
const int MAX_LOGIN_INFO_SIZE = 3; // loginInfoStore array entry count
```

In `config.cpp`

- `HostInfo` type is used to declare a variable that contains host computer name and port number.
- `LoginInfo` array contains a list of WiFi loginID/password and host computer in the network.

```C++
//
// Host computer name and port number
//
HostInfo host1("hostname1", PORT_NUMBER);
HostInfo host2("hostname2", PORT_NUMBER);
HostInfo host3("hostname3", PORT_NUMBER);

//
// WiFi login/pw and ClickCounter host to connect on the network
//
LoginInfo loginInfoStore[MAX_LOGIN_INFO_SIZE] {
  // ssid     password               host
  {"WiFi1",   "enter password here", &host1},
  {"WiFi2",   "enter password here", &host2},
  {"WiFi3",   "enter password here", &host3}
};
```

Note how `MAX_LOGIN_INFO_SIZE` is used above.  It has to match the list entry count.

ESP_click_counter will run through the items of the `loginInfoStore` list, trying to connect for 20 seconds each.

</td>
<td valign="top" width="50%" style="border-style: none">

### Báo hiệu

Để truyền tín hiệu đến máy tính ClickCounter, chúng tôi cần ID/mật khẩu đăng nhập WiFi và tên/cổng máy tính chủ.

Trong `config.h`, hai hằng số được xác định.

- `PORT_NUMBER` hiện giống nhau cho tất cả ClickCounter.
- `MAX_LOGIN_INFO_SIZE` được sử dụng để chỉ định số lượng mục nhập danh sách ID/mật khẩu đăng nhập WiFi.

```C++
//
// WiFi and host PC info variables
//
const int PORT_NUMBER = 8201;      // port number used for ClickCount service on Windows
const int MAX_LOGIN_INFO_SIZE = 3; // loginInfoStore array entry count
```

Trong `config.cpp`

- Kiểu `HostInfo` dùng để khai báo biến chứa tên máy tính chủ và số port.
- Mảng `LoginInfo` chứa danh sách ID/mật khẩu đăng nhập WiFi và máy chủ trong mạng.

```C++
//
// Host computer name and port number
//
HostInfo host1("hostname1", PORT_NUMBER);
HostInfo host2("hostname2", PORT_NUMBER);
HostInfo host3("hostname3", PORT_NUMBER);

//
// WiFi login/pw and ClickCounter host to connect on the network
//
LoginInfo loginInfoStore[MAX_LOGIN_INFO_SIZE] {
  // ssid     password               host
  {"WiFi1",   "enter password here", &host1},
  {"WiFi2",   "enter password here", &host2},
  {"WiFi3",   "enter password here", &host3}
};
```

Lưu ý việc sử dụng `MAX_LOGIN_INFO_SIZE` ở trên. Nó phải phù hợp với số lượng mục danh sách.

ESP_click_counter sẽ chạy qua các mục trong danh sách `loginInfoStore`, cố gắng kết nối từng mục trong vòng 20 giây.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

### User specified variables review

In sum, the variables that ___need to be user-specified___ for both button switch connection and signal transmission are

In `config.h`

```C++
// ESO32 pin connection variable
const uint8_t pinNumberButton = 27; // pin ID the switch is connected to

// WiFi and host PC info variables
const int MAX_LOGIN_INFO_SIZE = 1; // loginInfoStore array entry count
```

`PORT_NUMBER` need not change unless ClickCounter on Windows changes the port assignment.

In `config.cpp`

```C++
// Host computer name and port number
HostInfo host1("hostname1", PORT_NUMBER);

// WiFi login/pw and ClickCounter host to connect on the network
LoginInfo loginInfoStore[MAX_LOGIN_INFO_SIZE] {
  // ssid     password               host
  {"WiFi1",   "enter password here", &host1},
};
```

</td>
<td valign="top" width="50%" style="border-style: none">

### Xem xét các biến do người dùng chỉ định

Tóm lại, các biến ___cần được người dùng chỉ định___ cho cả kết nối công tắc nút và truyền tín hiệu là

Trong `config.h`

```C++
// ESO32 pin connection variable
const uint8_t pinNumberButton = 27; // pin ID the switch is connected to

// WiFi and host PC info variables
const int MAX_LOGIN_INFO_SIZE = 1; // loginInfoStore array entry count
```

`PORT_NUMBER` không cần thay đổi trừ khi ClickCounter trên Windows thay đổi việc gán cổng.

Trong `config.cpp`

```C++
// Host computer name and port number
HostInfo host1("hostname1", PORT_NUMBER);

// WiFi login/pw and ClickCounter host to connect on the network
LoginInfo loginInfoStore[MAX_LOGIN_INFO_SIZE] {
  // ssid     password               host
  {"WiFi1",   "enter password here", &host1},
};
```

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

## 5.2. Run the program

### Arduino IDE settings review

In the directory `C:\YIC\ESP32_click_counter\`, double lick `ESP32_click_counter.ino` to open the Arduino IDE.

The following items must be set before running the program. They tend to be unselected when environment changes, hence need to be checked often.

- Board selection\
  Tools > Board > esp32 > ESP32 Dev Module
- COM port selection\
  Tools > Port > COM#
- Serial Monitor window\
  Tools > Serial Monitor (Ctrl-Shift-M)
  - COM baud rate\
    115200 baud
  - Toggle Timestamp\
    Click the clock icon to grey mode

</td>
<td valign="top" width="50%" style="border-style: none">

## 5.2. Chạy chương trình

### Đánh giá cài đặt Arduino IDE

Trong thư mục `C:\YIC\ESP32_click_counter\`, nhấp đúp vào `ESP32_click_counter.ino` để mở Arduino IDE.

Các mục sau phải được đặt trước khi chạy chương trình. Chúng có xu hướng hư hỏng khi môi trường thay đổi nên cần được kiểm tra thường xuyên.

- Lựa chọn Board\
  Tools > Board > esp32 > ESP32 Dev Module
- Chọn cổng COM\
  Tools > Port > COM#
- Serial Monitor window\
  Tools > Serial Monitor (Ctrl-Shift-M)
  - Tốc độ truyền COM\
    115200 baud
  - Toggle Timestamp\
    Bấm vào biểu tượng đồng hồ để chuyển sang chế độ màu xám

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

### Compilation

Compile the program in one of two ways:

1. On the menu:\
   Sketch > Verify/Compile (Ctrl-R)
2. On the top toolbar, click on the first button showing the down arrow.

Compilation messages are shown on the `Output` window.

If a board is not selected, will result in an error:

```CMD
Compilation error:
Missing FQBN (Fully Qualified Board Name)
```

</td>
<td valign="top" width="50%" style="border-style: none">

### Biên soạn

Biên dịch chương trình theo một trong hai cách:

1. Trên menu:\
   Sketch > Verify/Compile (Ctrl-R)
2. Trên thanh công cụ trên cùng, nhấp vào nút đầu tiên hiển thị mũi tên xuống.

Thông báo biên dịch được hiển thị trên `Output` window.

Nếu board không được chọn thì sẽ xảy ra lỗi:

```CMD
Lỗi dịch thuật:
Thiếu FQBN (Tên hội đồng đủ tiêu chuẩn)
```

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

### Upload and execute

If it compiles, upload the program in one of two ways:

1. On the menu:\
   Sketch > Upload (Ctrl-U)
2. On the top toolbar, click on the second button showing the right arrow.

Upload messages are shown on the `Output` window.

If the ESP32 is not connected, will result in an error:

```CMD
A fatal error occurred: Could not open COM3, the port doesn't exist
Failed uploading: uploading error: exit status 2
```

After uploading, the Serial Monitor window will show an output similar to the follwing:

```CMD
01:35:30.331 -> Connecting to WiFi1 network... 0 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 1 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 2 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 3 second(s)
01:35:30.331 -> WiFi connection successful.
01:35:30.331 -> IP address: 10.216.77.137
01:35:30.331 -> Interrupt capture task ESP32 core 1
01:35:30.331 -> TCP send task ESP32 core 0 Serial 246863502882720
```

On each click of the button, the Serial Monitor window will show the click data in the following format

```CMD
01:19:29.777 -> firstTriggerTime 12341292
01:19:29.777 -> lastTriggerTime  12341437
01:19:29.777 -> Data 246863502882720_c1_f12341292_r12341437
```

If the connection to WiFi or host machine fails, it will print the error essage

```CMD
01:19:29.784 -> TCP connection failed hostname1 8201
```

</td>
<td valign="top" width="50%" style="border-style: none">

### Tải lên và thực thi

Nếu nó biên dịch, hãy tải chương trình lên theo một trong hai cách:

1. Trên menu:\
   Sketch > Upload (Ctrl-U)
2. Trên thanh công cụ trên cùng, nhấp vào nút thứ hai hiển thị mũi tên phải.

Thông báo tải lên được hiển thị trên `Output` window.

Nếu ESP32 không được kết nối sẽ dẫn đến lỗi:

```CMD
A fatal error occurred: Could not open COM3, the port doesn't exist
Failed uploading: uploading error: exit status 2
```

Sau khi upload lên, Serial Monitor window sẽ hiển thị kết quả tương tự như sau:

```CMD
01:35:30.331 -> Connecting to WiFi1 network... 0 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 1 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 2 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 3 second(s)
01:35:30.331 -> WiFi connection successful.
01:35:30.331 -> IP address: 10.216.77.137
01:35:30.331 -> Interrupt capture task ESP32 core 1
01:35:30.331 -> TCP send task ESP32 core 0 Serial 246863502882720
```

Mỗi lần nhấp vào nút, Serial Monitor window sẽ hiển thị dữ liệu nhấp chuột theo định dạng sau

```CMD
01:19:29.777 -> firstTriggerTime 12341292
01:19:29.777 -> lastTriggerTime  12341437
01:19:29.777 -> Data 246863502882720_c1_f12341292_r12341437
```

Nếu kết nối với WiFi hoặc máy chủ không thành công, nó sẽ in thông báo lỗi

```CMD
01:19:29.784 -> TCP connection failed hostname1 8201
```

</td>
</tr>
</table>
