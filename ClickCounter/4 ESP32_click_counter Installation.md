# 4. ESP32_click_counter Installation

## 1. Source file copy

There is one directory for ESP32_click_counter in the setup file:

- `\YIC\ESP32_click_counter\`

and 7 files in the directory

- `ESP32_click_counter.h`
- `ESP32_click_counter.ino`
- `interrupt.cpp`
- `interrupt.h`
- `config.cpp`
- `config.h`
- `WiFi_login_info.h`
- `WiFi_TCP.cpp`
- `WiFi_TCP.h`

Copy `\YIC\ESP32_click_counter\*` to `C:\YIC\ESP32_click_counter\`

## 2. Windows 11 driver update

For Windows 11, _not for windows 10_, a UART driver update is  needed (as of Octorber 2023) for the ESP32 unit to communicate with Windows 11.

1. Download the latest CP210x Universal Windows Driver\
<https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads>
2. Unzip the driver file to a directory
3. Inside the directory, right click on the `silabser.inf` file and select Install

## 3. Arduino IDE

If Arduino IDE is not installed, download and install

- <https://www.arduino.cc/en/software>

In the directory `C:\YIC\ESP32_click_counter\`, double lick on `ESP32_click_counter.ino` to open Arduino IDE.

Inside Arduino IDE, all files should be present as tabs.

### 3.1. General setup

On the menu:\
File > Preference > Settings (Ctrl-Comma) > Settings tab

- Sketchbook location:\
  `C:\YIC\ESP32_click_counter\`
- Mark all checkboxes

### 3.2. Install ESP32 board

Open the Boards Manager by one of the two ways:

1. On the menu:\
   Tools > Board > Boards Manager... (Ctrl-Shift-B)
2. On the left vertical toolbar of Arduino IDE, press the second button that looks like computer internal expansion card

Boards Manager pane will open between the left vertical toolbar and the code editor.

On top of the Boards Manager, in the textbox "Filter your search...", type in `esp32`. Two or more items will appear.

Install `esp32 by Espressif Systems`

On the menu, select:\
Tools > Board > esp32 > ESP32 Dev Module

### 3.3. Install Vector library

Open the Library Manager by one of the two ways:

1. On the menu:\
  Tools > Manage Libraries... (Ctrl-Shift-I)
2. On the left vertical toolbar of Arduino IDE, press the third button that looks like standing books

Library Manager pane will open between the left vertical toolbar and the code editor.

On top of the Library Manager, in the textbox "Filter your search...", type in `vector`. Several items will appear.

Install `Vector by Peter Polidoro`

### 3.4 Connect ESP32

Physically connect an ESP32 unit to the computer via USB-micro USB cable, then set the following items:

- COM port selection\
  This select the communication port to ESP32.

  On the menu, select:\
  Tools > Port > COM?

  There might be more than one COM? to choose from. Unplug ESP32 to see which one disappears, then plug in again to find the COM number assigned to ESP32.

- Serial Monitor window\
  Outputs values from ESP32 via serial communication channel of COM port.

  On the menu, select:\
  Tools > Serial Monitor (Ctrl-Shift-M)

  - Set the COM baud rate\
    Correct serial communication speed must be selected for Serial Monitor output.

    On the dropdown menu on the right side of Serial Monitor window, select `115200 baud`.

  - Toggle Timestamp\
    Displays the received time of the messages from ESP32.

    On the bottom window with `Serial Monitor` and `Output` tab, there are three button icons on the right side of the `Output` tab. Click on the second one with the clock image to grey mode.
