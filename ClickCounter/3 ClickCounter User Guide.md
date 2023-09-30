# 3. ClickCounter User Guide

Start ClickCount service by executing

```BASH
C:\> sc.exe start "ClickCounter"
```

in the Admin command-line window.

ClickCounter listens to the port __8201__ to receive the click data transmitted from ESP32, and appends it to the file:

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

[![Left Arrow](https://github.githubassets.com/images/icons/emoji/unicode/2b05.png?v8)](2%20ClickCounter%20Installation.md)\
[Previous: 2. ClickCounter Installation](2%20ClickCounter%20Installation.md)

[![Right Arrow](https://github.githubassets.com/images/icons/emoji/unicode/27a1.png?v8)](4%20ESP32_click_counter%20Installation.md)\
[Next: 4. ESP32_click_counter Installation](4%20ESP32_click_counter%20Installation.md)

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Main](../README.md)
