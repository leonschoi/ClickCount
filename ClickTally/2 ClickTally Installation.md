<table style="border-style: none" >
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

# 2. ClickTally Installation

## 1. Copy app files

There are three directories for ClickTally in the setup file:

- `\Program Files\YIC\ClickTally\`
- `\YIC\Config\`
- `\inetpub\wwwroot\Resources\`

Copy `\Program Files\YIC\ClickTally\*` to `C:\Program Files\YIC\ClickTally\`\
The files are

- `appsetting.json`
- `ClickTally.exe`
- `ClickTally.pdb`
- It will popup a dialog box saying `need to provide administrator permission`.  Press `Continue` to copy.

Copy `\YIC\Config\*` to `C:\YIC\Config\`\
The files are

- `DaysOfWeek.json`
- `ESP32ToStation.cache.json`
- `GoogleSheetsID.json`
- `TimeSlot.json`

Copy `\inetpub\wwwroot\Resources\*` to `C:\inetpub\wwwroot\Resources\`\
One file in the directory

- `YIC_Logo.ico`

</td>
<td valign="top" width="50%" style="border-style: none">

# 2. Cài đặt ClickTally

## 1. Sao chép file ứng dụng

Có ba thư mục dành cho ClickTally trong tệp cài đặt:

- `\Program Files\YIC\ClickTally\`
- `\YIC\Config\`
- `\inetpub\wwwroot\Resources\`

Sao chép `\Program Files\YIC\ClickTally\*` sang `C:\Program Files\YIC\ClickTally\`\
Các tập tin là

- `appsetting.json`
- `ClickTally.exe`
- `ClickTally.pdb`
- Nó sẽ hiển thị dialog box với nội dung `need to provide administrator permission`. Nhấp vào `Continue` để sao chép.

Sao chép `\YIC\Config\*` sang `C:\YIC\Config\`\
Các tập tin là

- `DaysOfWeek.json`
- `ESP32ToStation.cache.json`
- `GoogleSheetsID.json`
- `TimeSlot.json`

Sao chép `\inetpub\wwwroot\Resources\*` sang `C:\inetpub\wwwroot\Resources\`\
Một tập tin trong một thư mục

- `YIC_Logo.ico`

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

## 2. Directory creation and sharing

Create directories

- `C:\YIC\Template\`
- `C:\YIC\ClickTally\`

Enable sharing for the follwing directoies with appropriate Permissions (Full Control or Read/Write) for everyone or individual users as needed

- `C:\inetpub\wwwroot` shared as `ClickReport`\
  Some html files will need to be deleted later.
  - Also, if need to modify files in `C:\inetpub\wwwroot` often, add write previlege to the directory so as to avoid being asked for Admin permission every time a file is changed:\
  Right click on `C:\inetpub\wwwroot` > Properties > Security > Users > Edit > Users > Allow Write.
- `C:\YIC\Template\` shared as `ClickTemplate`\
  To load template Excel file
- `C:\YIC\` shared as `YIC`\
  To handle the Config, Data, and Log directories.\
  Already done in ClickCounter setup.

</td>
<td valign="top" width="50%" style="border-style: none">

## 2. Tạo và chia sẻ thư mục

Tạo thư mục

- `C:\YIC\Template\`
- `C:\YIC\ClickTally\`

Cho phép chia sẻ các thư mục khác với Permissions (Full Control hoặc Read/Write) thích hợp cho mọi người hoặc người dùng cá nhân nếu cần

- `C:\inetpub\wwwroot` được chia sẻ dưới dạng `ClickReport`\
  Một số tệp html sẽ cần được xóa sau này.
  - Ngoài ra, nếu bạn thường xuyên sửa đổi các tập tin trong `C:\inetpub\wwwroot`, hãy thêm đặc quyền write vào thư mục để tránh bị yêu cầu quyền Administrator mỗi khi bạn thay đổi tập tin:\
  Nhấp chuột phải vào `C:\inetpub\wwwroot` > Properties > Security > Users > Edit > Users > Write permission.
- `C:\YIC\Template\` được chia sẻ dưới dạng `ClickTemplate`\
  Để tải file Excel mẫu
- `C:\YIC\` được chia sẻ dưới dạng `YIC`\
  Để xử lý các thư mục Config, Data và Log.\
  Đã được thực hiện trong quá trình thiết lập ClickCounter.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

## 3. Install `ClickTally` as Windows Service (daemon)

- Type `cmd` (or `Command Prompt`) in the taskbar search box, matching apps will appear.
- Right click on `Command Prompt`, select `Run as administrator`.
- Run
  ```BASH
  > sc.exe create "ClickTally" ^
    binpath= ^
      "C:\Program Files\YIC\ClickTally\ClickTally.exe" ^
    start=delayed-auto
  ```
  to create `ClickTally` service.
   - `start=delayed-auto` makes `ClickTally` start automatically when the computer reboots.
   - `delayed-` makes it start after the critical system services start first.
- Run
  ```BASH
  > sc.exe start "ClickTally"
  ```
  to start running the service
- Other control commands are
  - `sc.exe stop "ClickTally"` to stop
  - `sc.exe delete "ClickTally"` to remove from the services list
- Running `ClickTally` creates directories `C:\YIC\ClickTally\Data` and `C:\YIC\ClickTally\Log`

</td>
<td valign="top" width="50%" style="border-style: none">

## 3. Cài đặt `ClickTally` làm Windows Service (daemon)

- Gõ `cmd` (hoặc `Command Prompt`) vào ô tìm kiếm trên taskbar, các ứng dụng phù hợp sẽ hiện ra.
- Nhấp chuột phải vào `Command Prompt`, chọn `Run as Administrator`.
- Chạy
  ```BASH
  > sc.exe create "ClickTally" ^
    binpath= ^
      "C:\Program Files\YIC\ClickTally\ClickTally.exe" ^
    start=delayed-auto
  ```
  để tạo `ClickTally` service.
  - `start=delayed-auto` làm cho `ClickTally` tự động khởi động khi máy tính khởi động lại.
  - `delayed-` khiến nó khởi động sau khi services hệ thống quan trọng khởi động trước.
- Chạy
  ```BASH
  > sc.exe start "ClickTally"
  ```
  để bắt đầu chạy service
- Các lệnh điều khiển khác là
  - `sc.exe stop "ClickTally"` để dừng
  - `sc.exe remove "ClickTally"` để xóa khỏi danh sách service
- Chạy `ClickTally` tạo thư mục `C:\YIC\ClickTally\Data` và `C:\YIC\ClickTally\Log`

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

## 4. Control `ClickTally` using the Services app

- Go to `Services` app (type `Services` in the taskbar search box).
- The list contains `ClickTally`.
- Right click on `ClickTally` to see `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

</td>
<td valign="top" width="50%" style="border-style: none">

## 4. Điều khiển `ClickTally` bằng ứng dụng Services
  
- Vào ứng dụng `Services` (gõ `Services` vào ô tìm kiếm trên thanh taskbar).
- Danh sách chứa `ClickTally`.
- Nhấp chuột phải vào `ClickTally` để xem `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

</td>
</tr>
</table>
