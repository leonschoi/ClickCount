# 0. General Overview

ClickCounter system consists of:

1. ESP32 modules with attached switch buttons, connected to a local network via WiFi and sending TCP/IP messages on each click of the button.
2. A Windows computer running a service (daemon) app, receiving TCP/IP messages from the ESP32 modules and saving them.

Actual processing of the saved data and the generation of the report is done by ClickTally, another service running on Windows.

Windows installation of ClickCounter is a straightforward setup of Windows for TCP/IP connection and command-line execution of Windows service creation.

ESP32 installation requires the connection from Windows to ESP32 module via Arduino IDE and the modification of ESP32 code to specify the computer name, network ID/password.

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Previous: Main](../README.md)

[![Right Arrow](https://github.githubassets.com/images/icons/emoji/unicode/27a1.png?v8)](1%20Windows%20Network%20Setup.md)\
[Next: 1. Windows Network Setup](1%20Windows%20Network%20Setup.md)
