<table style="border-style: none">
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

# Quick Start

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The ClickCounter System monitors workflow progress by capturing button click signals from machine stations and presenting a report of accumulated signals grouped by station and time interval.

</td>
<td valign="top" width="50%" style="border-style: none">

ClickCounter System giám sát tiến trình công việc bằng cách ghi lại tín hiệu nhấp nút từ máy trạm và trình bày báo cáo về các tín hiệu tích lũy được nhóm theo trạm và khoảng thời gian.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

It is structured so that users only need to provide Excel files as templates to base the report on. The ClickCounter System will record clicks and update the report, and save the report to the archive at the end of the day. Users can view reports and check progress through the ClickCounter website.

</td>
<td valign="top" width="50%" style="border-style: none">

Nó được cấu trúc sao cho người dùng chỉ cần cung cấp các tệp Excel dưới dạng templates để làm cơ sở cho báo cáo. ClickCounter System sẽ ghi lại các lần nhấp chuột và cập nhật báo cáo, đồng thời lưu báo cáo vào archive vào cuối ngày. Người dùng có thể xem báo cáo và kiểm tra tiến trình thông qua trang web ClickCounter.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The ClickCounter System runs on configurable business days and hours. The same Excel template files will be used for new reports the next day as long as the files remain in the folder. When an Excel file is deleted, reports related to that Excel file will stop updating.

</td>
<td valign="top" width="50%" style="border-style: none">

ClickCounter System chạy vào các ngày và giờ làm việc có thể định cấu hình. Các tệp template Excel tương tự sẽ được sử dụng cho các báo cáo mới vào ngày hôm sau miễn là các tệp vẫn còn trong thư mục. Khi một file Excel bị xóa, các báo cáo liên quan đến file Excel đó sẽ ngừng cập nhật.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 1. Template Excel File

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Excel files with cells labeled `station ID`-`time slot ID` (e.g. `st2-103`) are used as a template for the report:

</td>
<td valign="top" width="50%" style="border-style: none">

Các tệp Excel có các ô được gắn nhãn `station ID`-`time slot ID` (ví dụ: `st2-103`) được sử dụng làm template cho báo cáo:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/812202f5-c357-406c-a9a5-4a429a5adc5b" alt="Template" width="800"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

These Excel files are converted to HTML report files. The labeled cells in the report files are filled with click count from `station ID`, recorded during the time interval specified by `time slot ID`.

</td>
<td valign="top" width="50%" style="border-style: none">

Các tệp Excel này được chuyển đổi thành tệp báo cáo HTML. Các ô được gắn nhãn trong tệp báo cáo chứa đầy số lần nhấn từ `station ID`, được ghi lại trong khoảng thời gian được chỉ định bởi `time slot ID`.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The template Excel files that need to be converted to report HTML files are located in the `\"Hostname"\ClickTemplate\` directory. Files in this directory will be used to generate and update daily reports for as long as it remains there.

</td>
<td valign="top" width="50%" style="border-style: none">

Các tệp template Excel cần được chuyển đổi thành tệp HTML báo cáo nằm trong thư mục `\"Hostname"\ClickTemplate\`. Các tệp trong thư mục này sẽ được sử dụng để tạo và cập nhật báo cáo hàng ngày miễn là nó vẫn còn ở đó.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" width="100%" style="border-style: none">

## 2. Click Counter Webpage

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The ClickCounter webpage can be launched using `http://"Hostname"` on the local network (or `http://localhost` on the installed computer):

</td>
<td valign="top" width="50%" style="border-style: none">

Trang web ClickCounter có thể được khởi chạy bằng cách sử dụng `http://"Hostname"` trên mạng cục bộ (hoặc `http://localhost` trên máy tính đã cài đặt):

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCount.en/assets/29897968/434b95a8-3963-4135-9c62-71753f798df1" alt="ClickCounter webpage" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The files in the `Current` section are files being updated at the time of monitoring. The file names are displayed with the last updated time, and listed in decreasing chronological order so users can quickly verify update progress.

</td>
<td valign="top" width="50%" style="border-style: none">

Các file trong phần `Current` là các file đang được cập nhật tại thời điểm theo dõi. Tên file được hiển thị kèm theo thời gian cập nhật gần đây nhất và được liệt kê theo thứ tự thời gian giảm dần để người dùng có thể nhanh chóng xác minh tiến trình cập nhật.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The webpage is automatically refreshed once a second to show file update changes in real time. At the bottom of the page the last refresh time is shown.

</td>
<td valign="top" width="50%" style="border-style: none">

Trang web được tự động làm mới mỗi giây một lần để hiển thị các thay đổi cập nhật tệp trong thời gian thực. Ở cuối trang hiển thị thời gian làm mới lần cuối.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

At the end of the business day, `Current` files will move to the `Archive` section with the date added to the end of the file name.

</td>
<td valign="top" width="50%" style="border-style: none">

Vào cuối ngày làm việc, các tệp `Current` sẽ chuyển sang phần `Archive` với ngày được thêm vào cuối tên tệp.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The `Archive` section files are sorted in descending date order and the last updated time is no longer displayed.

</td>
<td valign="top" width="50%" style="border-style: none">

Các tệp phần `Archive` được sắp xếp theo thứ tự ngày giảm dần và thời gian cập nhật gần đây nhất không còn được hiển thị.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Each file name can be clicked to view the content. The clicked page will open in a new web browser tab.

</td>
<td valign="top" width="50%" style="border-style: none">

Mỗi tên tập tin có thể được nhấp vào để xem nội dung. Trang được nhấp sẽ mở trong tab trình duyệt web mới.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

## 3. Report Webpage

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Clicking on the report file name will open a new web browser tab displaying the report page. It contains the latest accumulated click count for cells matching the labels `station ID`-`time slot ID` in the template Excel file.

</td>
<td valign="top" width="50%" style="border-style: none">

Nhấp vào tên tệp báo cáo sẽ mở tab trình duyệt web mới hiển thị trang báo cáo. Nó chứa số lần nhấp tích lũy mới nhất cho các ô khớp với nhãn `station ID`-`time slot ID` trong tệp template Excel.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center" style="border-style: none">

<img src="https://github.com/leonschoi/ClickCounter.en/assets/29897968/ff65e9bf-ae72-48c6-9b7f-2e23b75500d3" alt="Report" width="800"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

If the page is too large, use Ctrl- to shrink the view.

</td>
<td valign="top" width="50%" style="border-style: none">

Nếu trang quá lớn, hãy sử dụng Ctrl- để thu nhỏ chế độ xem.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

## 4. Configuration Files

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

There are three parameters used to configure system behavior: one parameter for capturing click signals and two parameters for runtime scheduling.

</td>
<td valign="top" width="50%" style="border-style: none">

Có ba tham số được sử dụng để định cấu hình hành vi của hệ thống: một tham số để thu thập tín hiệu nhấp chuột và hai tham số để lập lịch thời gian chạy.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

These parameters are rarely changed, so it is not part of the daily workflow.

</td>
<td valign="top" width="50%" style="border-style: none">

Các thông số này hiếm khi được thay đổi nên nó không nằm trong quy trình làm việc hàng ngày.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

### 4.1. ESP32 ID to Station ID Mapping

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The ESP32 boards with button switches are used to send signals over Wi-Fi to the ClickCounter service (the service is a Windows process running in the background).

</td>
<td valign="top" width="50%" style="border-style: none">

ESP32 boards có một công tắc được sử dụng để gửi tín hiệu qua Wi-Fi đến ClickCounter service (service là một Windows process chạy trong nền).

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The ClickCounter service collects and saves signals and another service in the same machine named ClickTally processes the saved data to generate reports.

</td>
<td valign="top" width="50%" style="border-style: none">

ClickCounter service thu thập và lưu các tín hiệu và một service khác trong cùng một máy có tên ClickTally xử lý dữ liệu đã lưu để tạo báo cáo.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

The unique serial number of the ESP32 board is mapped to the machine's `station ID`. Mapping information is stored in GoogleSheets and downloaded when the ClickTally service starts. This website displays the latest mapping information obtained.

</td>
<td valign="top" width="50%" style="border-style: none">

Số sê-ri duy nhất của ESP32 board được ánh xạ tới `station ID` của máy. Thông tin bản đồ được lưu trữ trong GoogleSheets tính và được tải xuống khi dịch vụ ClickTally khởi động. Trang web này hiển thị thông tin bản đồ mới nhất thu được.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center"  style="border-style: none">

<img src="https://github.com/leonschoi/ClickCount.en/assets/29897968/eaef97c3-1770-4e02-b3ff-d1eacc0063eb" alt="ESP32" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

### 4.2. Work Days of the Week

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

Because the ClickTally service runs continuously in the background, it needs to know when not to process information. The working days of the week are specified in the file `C:\YIC\Config\DaysOfWeek.json`. The information currently used for processing is displayed on the website:

</td>
<td valign="top" width="50%" style="border-style: none">


Vì dịch vụ ClickTally chạy liên tục ở chế độ nền nên nó cần biết khi nào không nên xử lý thông tin. Các ngày làm việc trong tuần được chỉ định trong tệp `C:\YIC\Config\DaysOfWeek.json`. Thông tin hiện đang được sử dụng để xử lý được hiển thị trên trang web:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center"  style="border-style: none">

<img src="https://github.com/leonschoi/ClickCount.en/assets/29897968/c7cbd128-2fbf-41ce-92b0-5ff087a630e8" alt="Days" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

### 4.3. Work Time to Slot ID Mapping

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

In addition, because the process runs continuously in the background, it is necessary to clearly define the working time. _Work Time to Slot ID Mapping_ is used for the work time of the day and also to specify the time period for accumulating click count. It is stored in the file `C:\YIC\Config\TimeSlot.json`.

</td>
<td valign="top" width="50%" style="border-style: none">

Ngoài ra, do tiến trình chạy nền liên tục nên cần xác định rõ thời gian làm việc. _Work Time to Slot ID Mapping_ được sử dụng cho thời gian làm việc trong ngày và cũng để chỉ định khoảng thời gian tích lũy số lần nhấp chuột. Nó được lưu trữ trong tệp `C:\YIC\Config\TimeSlot.json`.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center"  style="border-style: none">

<img src="https://github.com/leonschoi/ClickCount.en/assets/29897968/720241fc-b152-4faa-9c68-a8746cebabe2" alt="Time Slot" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" style="border-style: none">

The slot time interval is measured from the specified time to the time of the next slot. Therefore, the last period with `None` as the `slot ID` is required to mark the end time of the last working slot, i.e. the end of the working day.

</td>
<td valign="top" width="50%" style="border-style: none">

Khoảng thời gian slot được tính từ thời điểm đã chỉ định đến thời điểm của slot tiếp theo. Do đó, khoảng thời gian cuối cùng có chữ `None` là `slot ID` là bắt buộc để đánh dấu thời gian kết thúc của slot làm việc cuối cùng, tức là kết thúc ngày làm việc.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

### 4.4. Work Calendar

</td>
</tr>
<tr style="border-style: none">
<td valign="top" style="border-style: none">

Combining information from _Work Days of the Week_ and _Work Time to Slot ID Mapping_, a calendar showing the weekly activity schedule is presented.

</td>
<td valign="top" width="50%" style="border-style: none">

Kết hợp thông tin từ _Work Days of the Week_ và _Work Time to Slot ID Mapping_, lịch hiển thị lịch hoạt động hàng tuần sẽ được trình bày.

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center"  style="border-style: none">

<img src="https://github.com/leonschoi/ClickCount.en/assets/29897968/e1d7190e-6109-4e89-8648-3a2a4527b539" alt="Calendar" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" style="border-style: none">

## 5. Log

</td>
</tr>
<tr style="border-style: none">
<td valign="top" style="border-style: none">

Daily process information and errors are written to the log file:

</td>
<td valign="top" width="50%" style="border-style: none">

Thông tin và lỗi quy trình hàng ngày được ghi vào tệp nhật ký:

</td>
</tr>
<tr style="border-style: none">
<td colspan=2 valign="top" align="center"  style="border-style: none">

<img src="https://github.com/leonschoi/ClickCount.en/assets/29897968/ff58c875-d2d6-409d-ae79-95a3fdfe260f" alt="Log" width="500"/>

</td>
</tr>
<tr style="border-style: none">
<td valign="top" style="border-style: none">

When this web page is opened or refreshed, it will automatically scroll to the bottom to display the latest information.

</td>
<td valign="top" width="50%" style="border-style: none">

Khi trang web này được mở hoặc làm mới, nó sẽ tự động cuộn xuống phía dưới để hiển thị thông tin mới nhất.

</td>
</tr>
</table>
