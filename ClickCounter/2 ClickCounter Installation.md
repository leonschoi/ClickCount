<table style="border-style: none">
<tr style="border-style: none">
<td valign="top" width="50%" style="color: border-style: none">

# 2. ClickCounter Installation

## 1. Copy app files

There is one directory for ClickCounter in the setup file:

- `\Program Files\YIC\ClickCounter\`

and three files in the directory

- `appsetting.json`
- `ClickCounter.exe`
- `ClickCounter.pdb`

Copy `\Program Files\YIC\ClickCounter\*` to `C:\Program Files\YIC\ClickCounter\`

It will popup a dialog box saying `need to provide administrator permission`.  Press `Continue` to copy.

## 2. Directory creation and sharing

Create a directory `C:\YIC\ClickCounter\`

Enable sharing for the follwing directoy with appropriate Permissions (Full Control or Read/Write) for everyone or individual users as needed

- `C:\YIC\` shared as `YIC`\
   To handle Data and Log files from other computers.

## 3. Install `ClickCounter` as Windows Service (daemon)

- Type `Windows PowerShell` (or `Command Prompt`) in the taskbar search box, matching apps will appear.
- Right click on `Windows PowerShell` (or `Command Prompt`), select `Run as administrator`.
- Run
  ```BASH
  C:\> sc.exe create "ClickCounter" binpath="C:\Program Files\YIC\ClickCounter\ClickCounter.exe" start=delayed-auto
  ```
  to create `ClickCounter` service.
   - `start=delayed-auto` makes `ClickCounter` start automatically when the computer reboots.
   - `delayed-` makes it start after the critical system services start first.
- Run
  ```BASH
  C:\> sc.exe start "ClickCounter"
  ```
  to start running the service
- Other control commands are
  - `sc.exe stop "ClickCounter"` to stop
  - `sc.exe delete "ClickCounter"` to remove from the services list
- Running `ClickCounter` creates directories `C:\YIC\ClickCounter\Data` and `C:\YIC\ClickCounter\Log`

## 4. Control `ClickCounter` using the Services app

- Go to the `Services` app (type `Services` in the taskbar search box).
- Services list contains `ClickCounter`.
- Right click on `ClickCounter` to see `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

</td>
<td valign="top" width="50%" style="border-style: none">

#2. Cài đặt ClickCounter

## 1. Sao chép file ứng dụng

Trong file cài đặt có thư mục dành cho ClickCounter:

- `\Program Files\YIC\ClickCounter\`

và ba tập tin trong thư mục

- `appsetting.json`
- `ClickCounter.exe`
- `ClickCounter.pdb`

Sao chép `\Program Files\YIC\ClickCounter\*` sang `C:\Program Files\YIC\ClickCounter\`

Nó sẽ bật lên một hộp thoại có nội dung `administrator permissions required`. Nhấp vào `Continue` để sao chép.

## 2. Tạo và chia sẻ thư mục

Tạo thư mục `C:\YIC\ClickCounter\`

Cho phép chia sẻ thư mục bổ sung với Quyền thích hợp (Toàn quyền kiểm soát hoặc Đọc/Ghi) cho mọi người hoặc người dùng cá nhân nếu cần

- `C:\YIC\` được chia sẻ dưới dạng `YIC`\
        Để xử lý các tệp Dữ liệu và Nhật ký từ các máy tính khác.

## 3. Cài đặt `ClickCounter` làm Dịch vụ Windows (daemon)

- Gõ `Windows PowerShell` (hoặc `Command Prompt`) vào hộp tìm kiếm trên thanh tác vụ, các ứng dụng phù hợp sẽ xuất hiện.
- Nhấp chuột phải vào `Windows PowerShell` (hoặc `Command Prompt`), chọn `Run as Administrator`.
- Chạy
  ```BASH
  C:\> sc.exe tạo "ClickCounter" binpath="C:\Program Files\YIC\ClickCounter\ClickCounter.exe" start=delayed-auto
  ```
  để tạo dịch vụ `ClickCounter`.
  - `start=delayed-auto` làm cho `ClickCounter` tự động khởi động khi máy tính khởi động lại.
  - `delayed-` khiến nó khởi động sau khi các dịch vụ hệ thống quan trọng khởi động trước.
- Chạy
  ```BASH
  C:\> sc.exe khởi động "ClickCounter"
  ```
  để bắt đầu chạy dịch vụ
- Các lệnh điều khiển khác là
  - `sc.exe stop "ClickCounter"` để dừng
  - `sc.exe delete "ClickCounter"` để xóa nó khỏi danh sách dịch vụ
- Chạy `ClickCounter` tạo thư mục `C:\YIC\ClickCounter\Data` và `C:\YIC\ClickCounter\Log`

## 4. Điều khiển `ClickCounter` bằng ứng dụng Services

- Vào ứng dụng `Services` (gõ `Services` vào ô tìm kiếm trên thanh taskbar).
- Danh sách dịch vụ chứa `ClickCounter`.
- Nhấp chuột phải vào `ClickCounter` để xem `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

</td>
</tr>
</table>
