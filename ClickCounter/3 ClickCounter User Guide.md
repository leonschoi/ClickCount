<table style="border-style: none" >
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

# 3. ClickCounter User Guide

</td>
<td valign="top" width="50%" style="border-style: none">

# 3. Hướng dẫn sử dụng ClickCounter

</td>
</tr>

<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none"></td>
<td valign="top" width="50%" style="border-style: none"></td>
</tr>

<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

If the ClickCount service has been manually stopped, start again by executing
```BASH
C:\> sc.exe start "ClickCounter"
```
in the Admin command-line window.

Because it was created with the option `start=delayed-auto`, it will start automatically when the computer boots up.

It can be stopped with command

```BASH
C:\> sc.exe stop "ClickCounter"
```

ClickCounter listens to the port __8201__ to receive the click data transmitted from ESP32 units, and appends them to the file:

`C:\YIC\ClickCounter\Data\clicks_YYYY-MM-DD-HH-MM.txt`

The time unit in the filename is in minutes. Each file will contain the data of 1 minute, so that ClickTally can check the directory once a minute and delete the file.

Note that a network directory for `C:\YIC` was created during the installation, hence it can be accessed as `\\"ComputerName"\YIC\ClickCounter\Data\`.

ClickCount service status can be checked with:

- `http://"ComputerName or IP"/log.html`\
  Updated in real time. This webpage contains both ClickCount and ClickTally log.
- Previous days' log messages are named\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`
- For more detailed error and info messages of ClickCount\
  `\\"ComputerName"\YIC\ClickCount\Log\log_YYYY-MM-DD.txt`\
  Updated in real time.

</td>
<td valign="top" width="50%" style="border-style: none">

Nếu ClickCount service đã bị dừng thủ công, hãy khởi động lại nó bằng cách thực thi
```BASH
C:\> sc.exe start "ClickCounter"
```
trong admin command-line window.

Vì nó được tạo bằng tùy chọn `start=delayed-auto` nên nó sẽ tự động khởi động khi máy tính khởi động.

Nó có thể được dừng lại bằng lệnh

```BASH
C:\> sc.exe stop "ClickCounter"
```

ClickCounter lắng nghe cổng __8201__ để nhận dữ liệu nhấp chuột được truyền từ thiết bị ESP32 và thêm chúng vào tệp:

`C:\YIC\ClickCounter\Data\clicks_YYYY-MM-DD-HH-MM.txt`

Đơn vị thời gian trong tên tệp là phút. Mỗi file sẽ chứa 1 phút dữ liệu nên ClickTally có thể kiểm tra thư mục mỗi phút một lần và xóa file.

Lưu ý rằng thư mục mạng cho `C:\YIC` đã được tạo trong quá trình cài đặt, vì vậy nó có thể được truy cập dưới dạng `\\"ComputerName"\YIC\ClickCounter\Data\`.

Trạng thái dịch vụ ClickCount có thể được kiểm tra bằng:

- `http://"ComputerName or IP"/log.html`\
  Cập nhật trong thời gian thực. Trang web này chứa cả nhật ký ClickCount và ClickTally.
- Tin nhắn nhật ký từ những ngày trước được đặt tên\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`
- Để biết thêm thông tin chi tiết về lỗi và thông báo ClickCount\
  `\\"ComputerName"\YIC\ClickCount\Log\log_YYYY-MM-DD.txt`\
  Cập nhật trong thời gian thực.

</td>
</tr>
</table>
