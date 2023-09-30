# 3. ClickCounter User Guide

If the ClickCount service has been manually stopped, start again by executing

```BASH
C:\> sc.exe start "ClickCounter"
```

in the Admin command-line window.

Because it was created with the option `start=delayed-auto`, it will start automatically when the computer boots up.

It can be stopped with command

```BASH
C:\> sc.exe stop "ClickCounter"
```

ClickCounter listens to the port __8201__ to receive the click data transmitted from ESP32 units, and appends them to the file:

`C:\YIC\ClickCounter\Data\clicks_YYYY-MM-DD-HH-MM.txt`

The filename time unit is in minutes. Each file will contain the data of 1 minute, so that ClickTally can check the directory once a minute and delete the file.

Note that a network directory for `C:YIC` was created during the installation, hence it can be accessed as `\\"ComputerName"\YIC\ClickCounter\Data\`.

ClickCount service status can be checked with:

- `http://"ComputerName or IP"/log.html`\
  Updated in real time. This webpage contains both ClickCount and ClickTally log.
- Previous days' log messages are named\
  `http://"ComputerName or IP"/log_YYYY-MM-DD.html`
- For more detailed error and info messages of ClickCount\
  `\\"ComputerName"\YIC\ClickCount\Log\log_YYYY-MM-DD.txt`\
  Updated in real time.
