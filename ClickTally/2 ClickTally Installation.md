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
      To handle Config, Data, and Log directories.\
      Already done in ClickCounter setup.

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
