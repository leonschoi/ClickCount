[Main](../README.md) > ClickTally > [1. Windows Network Setup](1%20Windows%20Web%20Server%20Setup.md)

# 1. Windows Web Server Setup

Set Windows Network Profile to private: [Windows Network Setup](../ClickCounter/1%20Windows%20Network%20Setup.md)

## Install IIS

- Go to `Turn Windows features on or off` app (type `windows features` in the taskbar search box)
- Find `Internet Information Services`.  Click once to enable it partially.
- Click `OK` to install.  This will create `C:\inetpub\wwwroot` directory.

## Open the WWW server port

- Go to the `Windows Defender Firewall with Advanced Security` app (type `defender` in the taskbar search box)
- On the center pane, select `World Wide Web Services (HTTP Traffic-in)`
- On the right, click `Enable Rule`

[![Left Arrow](https://github.githubassets.com/images/icons/emoji/unicode/2b05.png?v8)](0%20General%20Overview.md)\
[Previous: 0. General Overview](0%20General%20Overview.md)

[![Right Arrow](https://github.githubassets.com/images/icons/emoji/unicode/27a1.png?v8)](2%20ClickTally%20Installation.md)\
[Next: 2. ClickTally Installation](2%20ClickTally%20Installation.md)

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Main](../README.md)
