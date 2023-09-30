[Main](../README.md) > ClickTally > [2. ClickTally Installation](2%20ClickTally%20Installation.md)

# 2. ClickTally Installation

## 1. App file copy

There are three directories in the setup file:

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

Create `C:\YIC\Template\`\
Create `C:\YIC\ClickTally\`

## 2. Directory sharing and permissions

 Enable directory sharing with appropriate Permissions (Full Control or Read/Write) for everyone or individual users as needed

- `C:\inetpub\wwwroot` shared as `ClickReport`\
      Some html files will need to be deleted later.
   - Also, if need to modify files in `C:\inetpub\wwwroot` often, avoid being asked for Admin permission every time by right click > Properties > Security > Users > Edit > Users > Allow Write.
- `C:\YIC\Template\` shared as `ClickTemplate`\
      To load template Excel file
- `C:\YIC\` shared as `YIC`\
      To handle Config, Data, and Log directories.

## 3. Install `ClickTally` as Windows Service (daemon)

- Type `Windows PowerShell` (or `Command Prompt`) in the taskbar search box, matching apps will appear.
- Right click on `Windows PowerShell` (or `Command Prompt`), select `Run as administrator`.
- Run
  ```BASH
  C:\> sc.exe create "ClickTally" binpath="C:\Program Files\YIC\ClickTally\ClickTally.exe" start=delayed-auto
  ```
  to create `ClickTally` service.
   - `start=delayed-auto` makes `ClickTally` start automatically when the computer reboots.
   - `delayed-` makes it start after the critical system services start first.
- Run
  ```BASH
  C:\> sc.exe start "ClickTally"
  ``````
  to start running the service
- Other control commands are
  - `sc.exe stop "ClickTally"` to stop
  - `sc.exe delete "ClickTally"` to remove from the services list
- Running `ClickTally` creates directories `C:\YIC\ClickTally\Data` and `C:\YIC\ClickTally\Log`

## 4. Control `ClickTally` using the Services app

- Go to `Services` app (type `Services` in the taskbar search box).
- In the list it contains `ClickTally`.
- Right click on `ClickTally` to see `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

[![Left Arrow](https://github.githubassets.com/images/icons/emoji/unicode/2b05.png?v8)](1%20Windows%20Web%20Server%20Setup.md)\
[Previous: 1. Windows Web Server Setup](1%20Windows%20Web%20Server%20Setup.md)

[![Right Arrow](https://github.githubassets.com/images/icons/emoji/unicode/27a1.png?v8)](3%20ClickTally%20User%20Guide.md)\
[Next: 3. ClickTally User Guide](3%20ClickTally%20User%20Guide.md)

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Main](../README.md)
