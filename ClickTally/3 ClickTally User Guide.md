<table style="border-style: none" >
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

# 3. ClickTally User Guide

If the ClickTally service has been manually stopped, restart by executing

```BASH
C:\> sc.exe start "ClickTally"
```
in the Admin command-line window.

Because it was created with the option `start=delayed-auto`, it will start automatically when the computer boots.

It can be stopped by command

```BASH
C:\> sc.exe stop "ClickTally"
```

## 1. Daily usage of ClickTally

### 1.1. 7:00 am daily configuration loading

At 7:00 am (and also at the launch of the ClickTally service), there are two data sources that need to be present:

1. Template Excel file containing "station ID"-"time slot" (e.g., `st13-107`) cells to record click count accumulation.
2. ESP32 unit ID to station ID mapping

#### Template Excel file

The template Excel file is to be converted into a report webpage. It should be stored in the network directory:

- `\\"ComputerName"\ClickTemplate\`

The basename of the template file will be used as the report name. That is, if the template Excel file is stored as

- `\\"ComputerName"\ClickTemplate\"ReportName".xlsx` or `.xls`

The resulting report webpage will be

- `http://"ComputerName or IP"/"ReportName".html`

Note:

- If the template Excel file is not present, ClickTally will log error messages and keep waiting.
- If there are more than one Excel file in the directory, the most recently modified file will be used.

#### ESP32 unit ID to station ID mapping

ESP32 unit ID to station ID mapping info is obtained from `GoogleSheets` automatically with the URL specified in the configuration.

- If the Internet access is not available, it will keep trying until 7:05 am and then read from `\\"ComputerName"\YIC\Config\ESP32ToStation.cache.json`, which contains the last-updated cache data obtained from `GoogleSheets`.
- If both the Internet access and the cache file are missing,  ClickTally will log error messages and keep waiting.
- Currently used ESP32 unit ID to station ID mapping data is shown on the webpage\
  `http://"ComputerName or IP"/ESP32ToStation.html` for verification.

</td>
<td valign="top" width="50%" style="border-style: none">

# 3. Hướng dẫn sử dụng ClickTally

Nếu dịch vụ ClickTally đã bị dừng theo cách thủ công, hãy khởi động lại bằng cách thực thi

```BASH
C:\> sc.exe start "ClickTally"
```
trong cửa sổ dòng lệnh admin.

Vì nó được tạo bằng tùy chọn `start=delayed-auto` nên nó sẽ tự động khởi động khi máy tính khởi động.

Nó có thể được dừng lại bằng lệnh

```BASH
C:\> sc.exe stop "ClickTally"
```

## 1. Phương pháp sử dụng ClickTally mỗi ngày

### 1.1. Load cấu hình vào lúc 7h sáng hàng ngày

Vào lúc 7 giờ sáng (và cả khi ClickTally service bắt đầu), cần có hai nguồn dữ liệu:

1. Template Tệp Excel chứa các ô "station ID"-"time slot" (ví dụ: `st13-107`) để ghi lại số lần bấm nút tích lũy
2. Bảng chuyển đổi ID đơn vị ESP32 sang ID trạm

#### Template Tệp Excel

Template tệp Excel sẽ được chuyển thành trang web báo cáo. Nó sẽ được lưu trữ trong thư mục mạng:

- `\"ComputerName"\ClickTemplate\`

Tên cơ sở của tệp mẫu sẽ được sử dụng làm tên báo cáo. Tức là, nếu tệp template của Excel được lưu trữ dưới dạng

- `\"ComputerName"\ClickTemplate\"ReportName".xlsx` hoặc `.xls`

Tên trang web báo cáo là

- `http://"ComputerName or IP"/"ReportName".html`

Ghi chú:

- Nếu không có file template Excel, ClickTally sẽ ghi thông báo lỗi và tiếp tục chờ.
- Nếu có nhiều hơn một file Excel trong thư mục thì file sửa đổi gần đây nhất sẽ được sử dụng.

#### Chuyển đổi ID đơn vị ESP32 thành ID trạm

Thông tin ánh xạ ID đơn vị ESP32 tới ID trạm được tự động lấy từ `GoogleSheets` với URL được chỉ định trong cấu hình.

- Nếu không có kết nối Internet, nó sẽ tiếp tục thử cho đến 7:05 sáng rồi đọc từ `\"ComputerName"\YIC\Config\ESP32ToStation.cache.json`, chứa dữ liệu bộ nhớ đệm được cập nhật lần cuối thu được từ `GoogleSheets`.
- Nếu thiếu cả tệp truy cập Internet và tệp bộ đệm, ClickTally sẽ ghi lại các thông báo lỗi khi tiếp tục chờ.
- Bảng chuyển đổi ID đơn vị ESP32 sang ID trạm được hiển thị trên trang web\
  `http://"ComputerName or IP"/ESP32ToStation.html` để xác minh.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

### 1.2. Report generation

With the configuration data provided, ClickTally processes the data from ClickCounter, and the report is stored in the webpage:

- `http://"ComputerName or IP"/"ReportName".html`\
  Updated once every minute.
- Previous workdays' reports are named\
  `http://"ComputerName or IP"/"ReportName"_YYYY-MM-DD.html`

### 1.3 Status log

ClickTally service status can be checked with:

- `http://"ComputerName or IP"/log.html`\
  Updated in real time. This webpage contains both ClickTally and ClickCount log.
- Previous days' log messages are named\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`
- For more detailed error and info messages of ClickTally\
  `\\"ComputerName"\YIC\ClickTally\Log\log_YYYY-MM-DD.txt`\
  Updated in real time.

</td>
<td valign="top" width="50%" style="border-style: none">

### 1.2. Tạo báo cáo

Với dữ liệu cấu hình được cung cấp, ClickTally xử lý dữ liệu từ ClickCounter và báo cáo trên website:

- `http://"ComputerName or IP"/"ReportName".html`\
  Cập nhật mỗi phút một lần.
- Báo cáo ngày làm việc trước đó có tên\
  `http://"ComputerName or IP"/"ReportName"_YYYY-MM-DD.html`

### 1.3 Nhật ký trạng thái

Trạng thái dịch vụ ClickTally có thể được kiểm tra bằng:

- `http://"ComputerName or IP"/log.html`\
  Cập nhật trong thời gian thực. Trang web này chứa cả nhật ký ClickTally và ClickCount.
- Tin nhắn nhật ký từ những ngày trước được đặt tên\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`
- Để biết thêm thông tin và chi tiết lỗi của ClickTally\
  `\\"ComputerName"\YIC\ClickTally\Log\log_YYYY-MM-DD.txt`\
  Cập nhật trong thời gian thực.

</td>
</tr>
<tr style="border-style: none">
<td valign="top" width="50%" style="border-style: none">

## 2. Summary of the ClickTally Process

ClickTally collects data generated by ClickCounter and saves the processed data into a report webpage.

- When the ClickTally service starts, seldom-changed configuration data is read from the directory

   `\\"ComputerName"\YIC\Config\`

  Files read are:
  - `GoogleSheetsID.json`
  - `TimeSlot.json`
  - `\DaysOfWeek.json`

- At 7:00 am or when ClickTally service starts:
  
  The template Excel file to be transformed into the report webpage is read from

  - `\\"ComputerName"\ClickTemplate\"ReportName".xlsx` or `.xls`

  ESP32 ID to station ID mapping data is read from

  - `GoogleSheets` if the Internet is available
  - From the last-updated data cache file `\\"ComputerName"\YIC\Config\ESP32ToStation.cache.json` otherwise.\
    ESP32 ID to station ID mapping currently being used can seen in\
    `http://"ComputerName or IP"/ESP32ToStation.html`

- During work hours, ClickCounter data is read ___once a minute___ from the directory

  `\\"ComputerName"\YIC\ClickCounter\Data\`

  and the report written to

  `http://"ComputerName or IP"/"ReportName".html` and\
  `http://"ComputerName or IP"/"ReportName"_YYYY-MM-DD.html`

  Note that 7:00 am is considered the starting time of the day. ClickCounter data saved beween 12:00 am to 6:59 am is considered to be of previous day's event.

- The processed ClickCounter data files are deleted but the data is backed up in

  `\\"ComputerName"\YIC\ClickTally\Data\clicks_YYYY-MM-DD.txt`

  A short form of ClickTally's error and info messages are saved, along with ClickCounter's messages, in

  `http://"ComputerName or IP"/log.html`

  Previous days' log messages are named\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`

  And the detailed error and info messages of ClickTally are saved in

  `\\"ComputerName"\YIC\ClickTally\Log\log_YYYY-MM-DD.txt`

</td>
<td valign="top" width="50%" style="border-style: none">

## 2. Tóm tắt quy trình ClickTally

ClickTally thu thập dữ liệu do ClickCounter tạo và lưu dữ liệu đã xử lý vào trang web báo cáo.

- Khi dịch vụ ClickTally khởi động, dữ liệu cấu hình hiếm khi thay đổi sẽ được đọc từ thư mục

   `\"Tên máy tính"\YIC\Config\`

  Các tập tin được đọc là:
  - `GoogleSheetsID.json`
  - `TimeSlot.json`
  - `\DaysOfWeek.json`

- Lúc 7 giờ sáng hoặc khi ClickTally service bắt đầu:
  
  File template Excel sẽ được chuyển thành trang web báo cáo

  - `\"ComputerName"\ClickTemplate\"ReportName".xlsx` hoặc `.xls`

  Bảng chuyển đổi ID ESP32 sang ID trạm được đọc từ

  - `GoogleSheets` nếu có Internet
  - Từ tệp bộ nhớ đệm dữ liệu được cập nhật lần cuối `\"ComputerName"\YIC\Config\ESP32ToStation.cache.json` nếu không.\
    Có thể xem ánh xạ của ID ESP32 tới ID trạm hiện đang sử dụng trong\
    `http://"ComputerName or IP"/ESP32ToStation.html`

- Trong giờ làm việc, dữ liệu ClickCounter được đọc ___mỗi phút một lần___ từ thư mục

  `\\"ComputerName"\YIC\ClickCounter\Data\`

  và báo cáo được lưu trong tập tin

  `http://"ComputerName or IP"/"ReportName".html` và\
  `http://"ComputerName or IP"/"ReportName"_YYYY-MM-DD.html`


  Lưu ý rằng 7 giờ sáng được coi là thời điểm bắt đầu một ngày mới. Dữ liệu ClickCounter được lưu từ 12:00 sáng đến 6:59 sáng được coi là từ các sự kiện của ngày hôm trước.

- Tệp dữ liệu ClickCounter đã xử lý sẽ bị xóa nhưng dữ liệu được sao lưu

  `\\"ComputerName"\YIC\ClickTally\Data\clicks_YYYY-MM-DD.txt`

  Một dạng thông tin ClickTally ngắn gọn và thông báo lỗi được lưu trữ cùng với thông báo ClickCounter

  `http://"ComputerName or IP"/log.html`

  Tệp nhật ký của ngày hôm trước có tên\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`

  Và các thông báo và chi tiết lỗi ClickTally chi tiết được lưu trong

  `\\"ComputerName"\YIC\ClickTally\Log\log_YYYY-MM-DD.txt`

</td>
</tr>
</table>
