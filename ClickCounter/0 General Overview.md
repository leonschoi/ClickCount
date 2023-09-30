# 0. General Overview

ClickCounter system consists of:

1. ESP32 modules with attached switch buttons, connected to a local network via WiFi and sending TCP/IP messages on each click of the button.
2. A Windows computer running a service (daemon) app, receiving TCP/IP messages from the ESP32 modules and storing them.

Actual processing of the stored data and the generation of the report is done by ClickTally, another service running on Windows.

Windows installation of ClickCounter is a straightforward setup of Windows for TCP/IP connection and command-line execution of Windows service creation.

Since ClickCounter is written as a service, it runs silently in the background without a user interface until it is manually stopped.

And it is configured to start automatically when the computer turns on.  There is no need to separately run the process after the computer has been turned off.

ESP32 installation requires a USB connection from Windows to ESP32 module via Arduino IDE and the modification of ESP32 code to specify the computer name, network ID/password.
