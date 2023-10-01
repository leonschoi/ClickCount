<table style="border-style: none" >
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

# 1. Windows Web Server Setup

Set Windows Network Profile to private ([Windows Network Setup](../ClickCounter/1%20Windows%20Network%20Setup.md)) before setting up the Web Server.

## Install IIS

- Go to `Turn Windows features on or off` app (type `windows features` in the taskbar search box)
- Find `Internet Information Services`.  Click once to activate it partially.
- Click `OK` to install.  This will create the `C:\inetpub\wwwroot` directory.

## Open the WWW server port

- Go to the `Windows Defender Firewall with Advanced Security` app (type `defender` in the taskbar search box)
- On the center pane, select `World Wide Web Services (HTTP Traffic-in)`
- On the right, click `Enable Rule`

</td>
<td valign="top" width="50%" style="border-style: none">

# 1. Thiết lập máy chủ web Windows

Đặt Cấu hình Mạng Windows ở chế độ riêng tư ([Windows Network Setup](../ClickCounter/1%20Windows%20Network%20Setup.md)) trước khi thiết lập Máy chủ Web.

## Cài đặt IIS

- Vào ứng dụng `Turn Windows feature on or off` (gõ `windows feature` vào ô tìm kiếm trên taskbar)
- Tìm kiếm `Internet Information Services`. Bấm một lần để kích hoạt nó một phần.
- Nhấn `OK` để cài đặt. Điều này sẽ tạo thư mục `C:\inetpub\wwwroot`.

## Mở cổng máy chủ WWW

- Đi tới ứng dụng `Windows Defender Firewall with Advanced Security` (gõ `defender` vào hộp tìm kiếm trên thanh tác vụ)
- Ở khung giữa chọn `World Wide Web Services (HTTP Traffic-in)`
- Ở bên phải, nhấp vào `Enable Rules`

</td>
</tr>
</table>
