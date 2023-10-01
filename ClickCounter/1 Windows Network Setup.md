<table style="border-style: none">
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

# 1. Windows Network Setup

## 1. Local network

By ethernet cable or WiFi, connect Windows to local network.  ESP32 units will also need to connect to the same network.

</td>
<td valign="top" width="50%" style="border-style: none">

# 1. Thiết lập mạng Windows

## 1. Mạng cục bộ

Sử dụng cáp ethernet hoặc WiFi, kết nối Windows với mạng cục bộ. Các thiết bị ESP32 cũng sẽ cần kết nối với cùng một mạng.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

## 2. Set network profile to private

The computer's network Profile needs to be set to private so it can be found by other computers on the same network.

### In Windows 11

- Go to the `Settings` app (type `settings` in the taskbar search box)
- Select `Network & internet` on the left menu
- Select `Ethernet`
- Set `Network profile type` to `Private`
- Come back out to `Network & internet`
- Select `Advanced network settings`
- Select `Advanced sharing settings`
- On `Private networks`, make sure `Network discovery` is `On`

### In Windows 10

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

## 2. Đặt cấu hình mạng ở chế độ riêng tư

Cấu hình mạng máy tính của bạn cần được đặt ở chế độ Riêng tư để các máy tính khác trên cùng mạng có thể tìm thấy nó.

### Trong Windows 11

- Vào ứng dụng `Settings` (gõ `settings` vào hộp tìm kiếm trên thanh tác vụ)
- Chọn `Network & internet` ở menu bên trái
- Chọn `Ethernet`
- Đặt `Network profile type` thành `Private`
- Quay lại `Network & internet`
- Chọn `Advanced network settings`
- Chọn `Advanced sharing settings`
- Trên `Private Network`, đảm bảo `Network Discovery` được `On`

### Trong Windows 10

- Vào ứng dụng `Settings` (gõ `settings` vào hộp tìm kiếm trên thanh tác vụ)
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
<td valign="top" width="50%" style="border-style: none">

## 3. Open firewall port (8201) to listen for switch click transmission

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

## 3. Mở cổng tường lửa (8201) để nghe switch click truyền

- Đi tới ứng dụng `Windows Defender Tường lửa với Bảo mật nâng cao` (gõ `defender` vào hộp tìm kiếm trên thanh tác vụ)
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
