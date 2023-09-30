# 1. Windows Web Server Setup

Set Windows Network Profile to private ([Windows Network Setup](../ClickCounter/1%20Windows%20Network%20Setup.md)) before setting up Web Server.

## Install IIS

- Go to `Turn Windows features on or off` app (type `windows features` in the taskbar search box)
- Find `Internet Information Services`.  Click once to enable it partially.
- Click `OK` to install.  This will create `C:\inetpub\wwwroot` directory.

## Open the WWW server port

- Go to the `Windows Defender Firewall with Advanced Security` app (type `defender` in the taskbar search box)
- On the center pane, select `World Wide Web Services (HTTP Traffic-in)`
- On the right, click `Enable Rule`
