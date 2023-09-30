# 3. ClickTally User Guide

If the ClickTally service has been manually stopped, start again by executing

```BASH
> sc.exe start "ClickTally"
```

in the Admin command-line window.

Because it was created with the option `start=delayed-auto`, it will start automatically when the computer boots up.

It can be stopped with command

```BASH
C:\> sc.exe stop "ClickTally"
```

## 3.1. Daily usage of ClickTally

### 3.1.1. 7:00 am daily configuration loading

At 7:00 am (and also when the ClickTally service is started), there are two data sources that need to be present:

1. Template Excel file containing "station ID"-"time slot" (e.g., `st13-107`) cells to have click count written on.
2. ESP32 unit ID to station ID mapping

#### Template Excel file

The template Excel file is to be transformed into the report webpage. It should be stored in the network directory:

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

- If the Internet access is not available, it keeps trying until 7:05 am and then reads from `\\"ComputerName"\YIC\Config\ESP32ToStation.cache.json`, which contains the last-updated cache data from `GoogleSheets`.
- If both the Internet access and the cache file are missing,  ClickTally will log error messages and keep waiting.
- Currently used ESP32 unit ID to station ID mapping data is shown on the webpage\
  `http://"ComputerName or IP"/ESP32ToStation.html` for verification.

### 3.1.2. Report generation

With the configuration data provided, ClickTally processes the data from ClickCounter, and the report is stored in the webpage:

- `http://"ComputerName or IP"/"ReportName".html`\
  Updated once every minute.
- Previous workdays' reports are named\
  `http://"ComputerName or IP"/"ReportName"_YYYY-MM-DD.html`

### 3.1.3 Status log

ClickTally service status can be checked with:

- `http://"ComputerName or IP"/log.html`\
  Updated in real time. This webpage contains both ClickTally and ClickCount log.
- Previous days' log messages are named\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`
- For more detailed error and info messages of ClickTally\
  `\\"ComputerName"\YIC\ClickTally\Log\log_YYYY-MM-DD.txt`\
  Updated in real time.

## 3.2. Summary of the ClickTally Process

ClickTally gathers data produced by ClickCounter, and saves the processed data into a report webpage.

- When the ClickTally service starts, seldom-changed configuration data is read from the directory

   `\\"ComputerName"\YIC\Config\`

  Files read are:
  - `GoogleSheetsID.json`
  - `TimeSlot.json`
  - `\DaysOfWeek.json`

- At 7:00 am or when the ClickTally service starts:
  
  Template Excel file to be transformed into the report webpage is read from

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
