<table style="border-style: none">
<tr style="border-style: none">
<td valign="top" width="50%" style="color: border-style: none">

# 1. Windows Network Setup

## 1. Local network

By ethernet cable or WiFi, connect to local network.  ESP32 units will also need to connect to the same network.

## 2. Set network profile to private

The computer's Network Profile needs to be set to Private to be found by other computers on the same network.

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
- Come back out to `Network & internet`
- Select `Change advanced sharing options`
- On `Private/Network Discovery`, make sure `Turn on network discovery` and `Turn on automatic setup of network connected devices` are checked

## 3. Open a firewall port (8201) to listen to click switch transmission

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

#1. Thiết lập mạng Windows

## 1. Mạng cục bộ

Bằng cáp ethernet hoặc WiFi, kết nối với mạng cục bộ. Các thiết bị ESP32 cũng sẽ cần kết nối với cùng một mạng.

## 2. Đặt cấu hình mạng ở chế độ riêng tư

Cấu hình mạng máy tính của bạn cần được đặt thành Riêng tư để các máy tính khác trên cùng mạng có thể tìm thấy nó.

### Trong Windows 11

- Vào ứng dụng `Cài đặt` (gõ `settings` vào hộp tìm kiếm trên thanh tác vụ)
- Chọn `Mạng & internet` ở menu bên trái
- Chọn `Ethernet`
- Đặt `Loại hồ sơ mạng` thành `Riêng tư`
- Quay về `Mạng & Internet`
- Chọn `Cài đặt mạng nâng cao`
- Chọn `Cài đặt chia sẻ nâng cao`
- Trên `Private Network`, đảm bảo `Network Discovery` được `On`

### Trong Windows 10

- Vào ứng dụng `Cài đặt` (gõ `settings` vào hộp tìm kiếm trên thanh tác vụ)
- Chọn `Mạng & Internet`
- Chọn `Ethernet` (hoặc `Wifi`)
- Bấm vào nút `Properties` Ethernet
- Đặt `Hồ sơ mạng` thành `Riêng tư`
- Quay về `Mạng & Internet`
- Chọn `Thay đổi tùy chọn chia sẻ nâng cao`
- Trên `Quyền riêng tư/Khám phá mạng`, đảm bảo đã chọn `Bật khám phá mạng` và `Bật thiết lập tự động các thiết bị được kết nối mạng`

## 3. Mở cổng tường lửa (8201) để nghe switch click truyền

- Đi tới ứng dụng `Windows Defender Tường lửa với Bảo mật nâng cao` (gõ `defender` vào hộp tìm kiếm trên thanh tác vụ)
- Ở khung bên trái chọn `Inbound Rules`
- Ở khung bên phải, nhấp vào `Quy tắc mới...`
- Cửa sổ `Trình hướng dẫn quy tắc gửi đến mới` sẽ mở ra.
- Chọn `Port`, sau đó nhấn `Next >`
- Chọn `TCP`, và `Specific localports:` gõ __`8201`__, sau đó `Next >`
- Chọn hộp radio `Cho phép kết nối`, sau đó `Tiếp theo >`
- Chọn `Domain` và `Private`, bỏ chọn `Public`, sau đó `Next >`
- Tên: `ClickCounter`, rồi `Finish`

</td>
</tr>
</table>
