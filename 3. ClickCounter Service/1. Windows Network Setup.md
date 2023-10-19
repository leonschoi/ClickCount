<table style="border-style: none">
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

# 1. Windows Network Setup

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Setup and installation must be done from an Administrator account.

</td>
<td valign="top" width="50%" style="border-style: none">

Việc thiết lập và cài đặt phải được thực hiện từ tài khoản Quản trị viên.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 1. Local network

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

By ethernet cable or WiFi, connect Windows to local network.  ESP32 units will also need to connect to the same network.

</td>
<td valign="top" width="50%" style="border-style: none">

Bằng cáp ethernet hoặc Wi-Fi, kết nối Windows với mạng cục bộ. Các thiết bị ESP32 cũng sẽ cần kết nối với cùng một mạng.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 2. Set network profile to private

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

This network profile setting was also done at [Windows Web Server Setup](../1.%20ClickCounter%20Website/1.%20Windows%20Web%20Server%20Setup.md) in chapter 1. ClickCounter Website.

The computer's Network Profile needs to be set to private so it can be found by other computers on the same network.

</td>
<td valign="top" width="50%" style="border-style: none">

Cài đặt network_profile này cũng được thực hiện tại [Windows Web Server Setup](../1.%20ClickCounter%20Website/1.%20Windows%20Web%20Server%20Setup.md) trong chương 1. ClickCounter Website.

Network Profile của máy tính cần được đặt ở chế độ riêng tư để các máy tính khác trên cùng network có thể tìm thấy nó.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

### In Windows 11

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Go to the `Settings` app (type `settings` in the taskbar search box)
- Select `Network & internet` on the left menu
- Select `Ethernet`
- Set `Network profile type` to `Private`
- Come back out to `Network & internet`
- Select `Advanced network settings`
- Select `Advanced sharing settings`
- On `Private networks`, make sure `Network discovery` is `On`

</td>
<td valign="top" width="50%" style="border-style: none">

- Vào ứng dụng `Settings` (gõ `settings` vào hộp tìm kiếm taskbar)
- Chọn `Network & internet` ở menu bên trái
- Chọn `Ethernet`
- Đặt `Network profile type` thành `Private`
- Quay lại `Network & internet`
- Chọn `Advanced network settings`
- Chọn `Advanced sharing settings`
- Trên `Private Network`, đảm bảo `Network Discovery` được `On`

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

### In Windows 10

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Go to the `Settings` app (type `settings` in the taskbar search box)
- Select `Network & Internet`
- Select `Ethernet` (or `Wifi`)
- Click on the Ethernet `Properties` button
- Set `Network profile` to `Private`
- Come back out to `Network & Internet`
- Select `Change advanced sharing options`
- On `Private/Network Discovery`, make sure `Turn on network discovery` and `Turn on automatic setup of network connected devices` are checked

</td>
<td valign="top" width="50%" style="border-style: none">

- Vào ứng dụng `Settings` (gõ `settings` vào hộp tìm kiếm taskbar)
- Chọn `Network & Internet`
- Chọn `Ethernet` (hoặc `Wifi`)
- Bấm vào nút `Properties` Ethernet
- Đặt `Network profile` thành `Private`
- Quay lại `Network & Internet`
- Chọn `Change advanced sharing options`
- Trên `Private/Network Discovery`, đảm bảo đã chọn `Turn on network discovery` và `Turn on automatic setup of network connected devices`

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 3. Open firewall port (8201) to listen for switch click transmission

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Go to the `Windows Defender Firewall with Advanced Security` app (type `defender` in the taskbar search box)
- On the left pane, select `Inbound Rules`
- On the right pane, click `New Rule...`
- `New Inbound Rule Wizard` window will open.
- Select `Port`, then click `Next >`
- Select `TCP`, and `Specific local ports:` type __`8201`__, then `Next >`
- Selct `Allow the connection` radio box, then `Next >`
- Select `Domain` and `Private`, unselect `Public`, then `Next >`
- Name: `ClickCounter`, then `Finish`

</td>
<td valign="top" width="50%" style="border-style: none">

- Đi tới ứng dụng `Windows Defender Firewall with Advanced Security` (gõ `defender` vào hộp tìm kiếm trên thanh tác vụ)
- Ở khung bên trái chọn `Inbound Rules`
- Ở khung bên phải, nhấp vào `New Rule...`
- Cửa sổ `New Inbound Rule Wizard` sẽ mở ra.
- Chọn `Port`, sau đó nhấn `Next >`
- Chọn `TCP`, và `Specific localports:` gõ __`8201`__, sau đó `Next >`
- Chọn hộp radio `Allow the connection`, sau đó `Next >`
- Chọn `Domain` và `Private`, bỏ chọn `Public`, sau đó `Next >`
- Tên: `ClickCounter`, rồi `Finish`

</td>
</tr>
</table>
