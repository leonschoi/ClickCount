[Main](../README.md) > ClickCounter > [1. Windows Network Setup](1%20Windows%20Network%20Setup.md)

# 1. Windows Network Setup

## 1. Local network

By ethernet cable or WiFi, connect to local network.  ESP32 will also need to connect to the same network.

## 2. Set network profile to private

The computer's Network Profile needs to be set to Private to be found by other computers on the same network.

### In Windows 11

- Go to the `Settings` app (type `settings` in the taskbar search box)
- Select `Network & internet` on the left menu
- Select `Ethernet`
- Set `Network profile type` to `Private`
- Come back out to `Network & internet`
- Select `Advanced network settings`
- Select `Advanced sharing settings`
- On Private networks, make sure `Network discovery` is `On`

### In Windows 10

- Go to the `Settings` app (type `settings` in the taskbar search box)
- Select `Network & Internet`
- Select `Ethernet` (or `Wifi`)
- Click on the Ethernet Properties button
- Set `Network profile` to `Private`
- Come back out to `Network & internet`
- Select `Change advanced sharing options`
- On Private/Network Discovery, make sure `Turn on network discovery` and `Turn on automatic setup of network connected devices` are checked

## 3. Open a firewall port (8201) to listen to click switch transmission

- Go to the `Windows Defender Firewall with Advanced Security` app (type `defender` in the taskbar search box)
- On the left pane, select `Inbound Rules`
- On the right pane, click `New Rule...`
- `New Inbound Rule Wizard` window will open.
- Select `Port`, then click `Next >`
- Select `TCP`, and `Specific local ports:` type __`8201`__, then `Next >`
- Selct `Allow the connection` radio box, then `Next >`
- Select `Domain` and `Private`, unselect `Public`, then `Next >`
- Name: `ClickCounter`, then `Finish`

[![Left Arrow](https://github.githubassets.com/images/icons/emoji/unicode/2b05.png?v8)](0%20General%20Overview.md)\
[Previous: 0. General Overview](0%20General%20Overview.md)

[![Right Arrow](https://github.githubassets.com/images/icons/emoji/unicode/27a1.png?v8)](2%20ClickCounter%20Installation.md)\
[Next: 2. ClickCounter Installation](2%20ClickCounter%20Installation.md)

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Main](../README.md)
