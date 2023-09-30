# 2. ClickCounter Installation

## 1. App file copy

There is one directory in the setup file:

- `\Program Files\YIC\ClickCounter\`

and three files in the directory

- `appsetting.json`
- `ClickCounter.exe`
- `ClickCounter.pdb`

Copy `\Program Files\YIC\ClickCounter\*` to `C:\Program Files\YIC\ClickCounter\`

It will popup a dialog box saying `need to provide administrator permission`.  Press `Continue` to copy.

## 2. Data directory creation

Create a directory `C:\YIC\ClickCounter\`

Enable directory sharing with appropriate Permissions (Full Control or Read/Write) for everyone or individual users as needed

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

- Go to `Services` app (type `Services` in the taskbar search box).
- The services list contains `ClickCounter`.
- Right click on `ClickCounter` to see `Start`, `Stop`, `Pause`, `Resume`, `Restart`.

[![Left Arrow](https://github.githubassets.com/images/icons/emoji/unicode/2b05.png?v8)](1%20Windows%20Network%20Setup.md)\
[Previous: 1. Windows Network Setup](1%20Windows%20Network%20Setup.md)

[![Right Arrow](https://github.githubassets.com/images/icons/emoji/unicode/27a1.png?v8)](3%20ClickCounter%20User%20Guide.md)\
[Next: 3. ClickCounter User Guide](3%20ClickCounter%20User%20Guide.md)

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Main](../README.md)
