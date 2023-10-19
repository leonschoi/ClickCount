<table style="border-style: none">
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

# 2. ClickCounter Installation

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Setup and installation must be done from an Administrator account.

The installation files can come from a USB drive or a download. For this tutorial, it is assumed to be located in the `C:\YIC\Setup\` directory.

</td>
<td valign="top" width="50%" style="border-style: none">

Việc thiết lập và cài đặt phải được thực hiện từ tài khoản Quản trị viên.

Các tập tin cài đặt có thể đến từ ổ USB hoặc bản tải xuống. Đối với hướng dẫn này, nó được cho là nằm trong thư mục `C:\YIC\Setup\`.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 1. Directory creation and sharing

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Create directory `C:\YIC\`.

Enable sharing for the directory `C:\YIC\` as `YIC` with Change/Write permissions for the users.

Create directory `C:\YIC\ClickCounter\`.

</td>
<td valign="top" width="50%" style="border-style: none">

Tạo thư mục `C:\YIC\`

Cho phép chia sẻ thư mục `C:\YIC` dưới dạng `YIC` với quyền Change/Write cho người dùng.

Tạo thư mục `C:\YIC\ClickCounter\`

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 2. Copy app files

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

There is one directory for ClickCounter in the setup file:

- `\Setup\Program Files\YIC\ClickCounter\`

and three files in the directory

- `appsetting.json`
- `ClickCounter.exe`
- `ClickCounter.pdb`

Copy `\Setup\Program Files\YIC\ClickCounter\*` to `C:\Program Files\YIC\ClickCounter\`

It will popup a dialog box saying `need to provide administrator permission`.  Press `Continue` to copy.

If `ClickCounter` service is already running, it will pop up a dialog box saying `the folder or a file in it is open in another program`. It needs to run `sc.exe stop "ClickCounter"`. See below for the Windows service stop command.

</td>
<td valign="top" width="50%" style="border-style: none">

Trong file cài đặt có thư mục dành cho ClickCounter:

- `\Setup\Program Files\YIC\ClickCounter\`

và ba tập tin trong thư mục

- `appsetting.json`
- `ClickCounter.exe`
- `ClickCounter.pdb`

Sao chép `\Setup\Program Files\YIC\ClickCounter\*` sang `C:\Program Files\YIC\ClickCounter\`

Nó sẽ bật lên một dialog box nói rằng `need to provide administrator permission`. Nhấp vào `Continue` để sao chép.

Nếu dịch vụ `ClickCounter` đang chạy, nó sẽ bật lên một hộp thoại cho biết `the folder or a file in it is open in another program`. Nó cần chạy `sc.exe stop "ClickCounter"`. Xem bên dưới để biết lệnh dừng dịch vụ Windows.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 3. Install `ClickCounter` as Windows Service (daemon)

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Type `cmd` (or `Command Prompt`) in the taskbar search box, matching apps will appear.
- Right click on `Command Prompt`, select `Run as administrator`.
- Run

</td>
<td valign="top" width="50%" style="border-style: none">

- Gõ `cmd` (hoặc `Command Prompt`) vào ô tìm kiếm taskbar, các ứng dụng phù hợp sẽ hiện ra.
- Nhấp chuột phải vào `Command Prompt`, chọn `Run as Administrator`.
- Chạy

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

  ```BASH
  > sc.exe create "ClickCounter" ^
    binpath= ^
      "C:\Program Files\YIC\ClickCounter\ClickCounter.exe" ^
    start=delayed-auto
  ```
</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

  to create `ClickCounter` service.
   - `start=delayed-auto` makes `ClickCounter` start automatically when the computer reboots.
   - `delayed-` makes it start after critical system services start first.
- Run

</td>
<td valign="top" width="50%" style="border-style: none">

  để tạo `ClickCounter` service.
   - `start=delayed-auto` làm cho `ClickCounter` tự động khởi động khi máy tính khởi động lại.
   - `delayed-` khiến nó khởi động sau khi services hệ thống quan trọng khởi động trước.
- Chạy

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">


  ```BASH
  C:\> sc.exe start "ClickCounter"
  ```
</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

  to start running the service
- Other control commands are
  - `sc.exe stop "ClickCounter"` to stop
  - `sc.exe delete "ClickCounter"` to remove from the services list. A service needs to be stopped before deleted.
- Running `ClickCounter` creates directories `C:\YIC\ClickCounter\Data` and `C:\YIC\ClickCounter\Log`

</td>
<td valign="top" width="50%" style="border-style: none">
 

  để bắt đầu chạy service
- Các lệnh điều khiển khác là
  - `sc.exe stop "ClickCounter"` để dừng
  - `sc.exe delete "ClickCounter"` để xóa khỏi danh sách services. Một service cần phải được dừng trước khi xóa.
- Chạy `ClickCounter` tạo các thư mục `C:\YIC\ClickCounter\Data` và `C:\YIC\ClickCounter\Log`

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 4. Control `ClickCounter` using the Services app

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

- Go to the `Services` app (type `Services` in the taskbar search box).
- The Services list contains `ClickCounter`.
- Right click on `ClickCounter` to see `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

</td>
<td valign="top" width="50%" style="border-style: none">

- Vào ứng dụng `Services` (gõ `Services` vào ô tìm kiếm trên thanh taskbar).
- Danh sách Services chứa `ClickCounter`.
- Nhấp chuột phải vào `ClickCounter` để xem `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

</td>
</tr>
</table>
