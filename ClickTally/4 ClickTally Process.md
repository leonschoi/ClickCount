# 4. ClickTally Process

This section explains the ClickTally process in detail.

## 4.1. Directories and files used

### Network Directories

To access the files, 3 network directories are created:

- `\\"ComputerName"\ClickReport` for `C:\inetpub\wwwroot\`
- `\\"ComputerName"\ClickTemplate` for `C:\YIC\ClickTally\Template`
- `\\"ComputerName"\YIC` for `C:\YIC`

### Input and Configuration Directories
  
   1. `C:\YIC\ClickCounter\Data\`

      Contains click data saved by `ClickCounter` with the name format `clicks_YYYY-MM-DD-HH-MM.txt`. These are read and ___deleted___ by `ClickTally` as it runs every minute.

   2. `C:\YIC\Config\`

      Contains `*.json` configuration files used at the start of the service and at daily 7 am update.  These will rarely be modified.

   3. `C:\YIC\Template\`, shared as `ClickTemplate`

      Contains `"ReportName".xlsx` or `*.xls` file used as a template to form the html report of the day. It is read at 7 am or at the start of the service.

### Report and Log Output Directories

   1. `C:\inetpub\wwwroot\`, shared as `ClickReport`

      Contains the result and status webpages

      - Today's result webpage is named `"ReportName".html`, previous days' reports are named `"ReportName"_YYYY-MM-DD.html`
      - Today's error and info log webpage is `log.html`, previous days' logs are in `log_YYYY-MM-DD.html`
      - `ESP32ToStation.html` shows ESP32 ID to station ID mapping currently being used.
      - The files with a date in the filename will keep accumulating and will need to be deleted manually.

   2. `C:\YIC\ClickTally\Data\`

      - Data read from `C:\YIC\ClickCounter\Data\clicks_YYYY-MM-DD-HH-MM.txt` files (which are deleted as they are processed) are backed up in `clicks_YYYY-MM-DD.txt`.
      - The files with a date in the filename will keep accumulating and will need to be deleted manually.

   3. `C:\YIC\ClickTally\Log`
      - Contains daily log of detailed error and info messages `log_YYYY-MM-DD.txt`.
      - The files with a date in the filename will keep accumulating and will need to be deleted manually.

## 4.2. Process in detail

### 4.2.1. Startup configuration loading

The following configuration files are loaded only when the ClickTally service starts

- `\\"ComputerName"\YIC\Config\GoogleSheetsID.json`
- `\\"ComputerName"\YIC\Config\TimeSlot.json`
- `\\"ComputerName"\YIC\Config\DaysOfWeek.json`

#### `GoogleSheetsID.json`

It contains the ID of the Google spreadsheet URL containing ESP32 ID to station ID mapping. For example:

```JSON
{
  "ID" :  "1fTyc-_XgesdMfqak7RS8RJ7WvYlmS-yxsH_Za3sc3V0"
}
```

#### `TimeSlot.json`

It contains the starting time corresponding to the time slot ID used in the template Excel file:

```JSON
{
  "700": "101",
  "830": "102",
  "930": "103",
  "1030": "104",
  "1230": "105",
  "1330": "106",
  "1430": "107",
  "1530": "108",
  "1630": "109",
  "1730": "110",
  "1830": "111",
  "1930": "112",
  "2030": "None"
}
```

- Time slot 101 starts from 7:00 to account for the work that might begin before 7:30:00, and ends at 8:29:59.
- Time slot 104 covers click counts from 10:30 to 12:29:59.
- Time slot "None" covers click counts from 20:30:00 to 6:59:59, and the slot marked "None" ___are not recorded___.

ClickTally considers the starting time of `TimeSlot.json` to be the start of the day.  Therefore if the clicks were saved between 00:00 and 6:59:59, they would be considered of the previous day.

"None" can be written as "N", "No", or "None".

#### `DaysOfWeek.json`

It contains working day specification:

```JSON
{
  "Monday": "Y",
  "Tuesday": "Y",
  "Wednesday": "Y",
  "Thursday" : "Y",
  "Friday" : "Y",
  "Saturday" : "N",
  "Sunday" : "N"
}
```

Day of the week can be specified in the format of whole spelling (Monday, ...), 3-letters (Mon, Tue, ...), or mininum characters (M, T, W, Th, F, Sa, Su).

Yes/No can be specified as Yes/No or Y/N.

#### Startup configuration loading

Note that the data in these three files are not the type that is updated frequently. Hence they are read only when the ClickTally service is started.

Wrong values in these `*.json` files will result in error log entry and the service exit.

### 4.2.2. 7:00 am daily configuration loading

7:00 am, or the first time specified in `TimeSlot.json` is considered the starting time of the day for all ClickTally processes.  Everything that happens beween 12:00 am to 6:59 am is considered to be of previous day's event.

At 7:00 am or when the ClickTally service starts, on a working day (as specified in `DaysOfWeek.json` above), two additional configuration files are loaded.

1. Template Excel file
2. ESP32 ID to station ID mapping

Note that these two operations are not run on non-working days, even if the service is restarted.

#### 1. Template Excel file conversion to report webpage

The template Excel file, containing cells with "station ID"-"time slot" (e.g., `st13-107`) identifiers, must be stored in the network directory `ClickTemplate`

- `\\"ComputerName"\ClickTemplate\`

ClickTally cannot work without a report file to write on, hence it will continuously log error messages until a template Excel file appears in the `ClickTemplate` directory.

If there are more than one file in the `ClickTemplate` directory, the most recently modified file will be used.

The basename of the template file determines the report file name:

- `\\"ComputerName"\ClickTemplate\"ReportName".xlsx` is converted to\
`http://"ComputerName or IP"/"ReportName".html`

ClickTally creates `"ReportName".html` and `"ReportName"_YYYY-MM-DD.html` at 7:00 am, and updates both as ClickCounter data is processed.

Also at 7:00 am, it checks the file of previous date `"PrevReportName"_YYYY-MM-dd.html` and deletes the corresponding webpage name without the date: `"PrevReportName".html`.

This avoids the confusion of finding the report file of the previous day when many files are present in the directory.

After 7 am, if the service is restarted, ClickTally checks for the existence of `"ReportName".html` and `"ReportName_YYYY-MM-DD.html`.  If these files exist, it keeps updating on the existing files.  If not, it creates new ones.

#### 2. ESP32 ID to station ID mapping read from GoogleSheets

GoogleSheets URL ID is obtained from `GoogleSheetsID.json` when the service is started.  If the ID is changed, the service must be restarted.

When the data is read from GoogleSheets, it saves to `C:\YIC\Config\ESP32ToStation.cache.json` and `http://"ComputerName or IP"/ESP32ToStation.html`.

ClickTally will try to obtain the data from GoogleSheets for 5 minutes.  If it cannot be obtained, it will read from `C:\YIC\Config\ESP32ToStation.cache.json` and start processing the ClickCounter data.

If neither GoogleSheets nor `C:\YIC\Config\ESP32ToStation.cache.json` is accessible, it will log error messages and wait for one of these two to appear.

### 4.2.3. Report generation

With all the configuration data provided, ClickTally will gather data from ClickCounter output

`C:\YIC\ClickCounter\Data\clicks_YYYY-MM-DD-HH-MM-txt`

Then delete the file, append the data read to `C:\YIC\ClickTally\Data\clicks_YYYY-MM-DD.txt`, and update the webpages

- `http://"ComputerName or IP"/"ReportName".html` and\
  `http://"ComputerName or IP"/"ReportName"_YYYY-MM-DD.html`

This process is run once every minute.

Again note that 7:00 am is the starting time of the day for the processes. If anythiing happens beween 12:00 am and 6:59 am, it is considered to be of previous day's event.

### 4.2.4. Status log

Simpliefied error and info messages are written in

- `http://"ComputerName or IP"/log.html`\
  Updated in real time. This webpage contains both ClickTally and ClickCount log.

Previous days' log messages will be stored in

- `http://"ComputerName or IP"/log_YYYY-MM-DD.html`

For more detailed error and info messages of ClickTally

- `\\"ComputerName"\YIC\ClickTally\Log\log_YYYY-MM-DD.txt`
