[Main](../README.md) > ClickCounter > [4. ESP32_click_counter Installation](4%20ESP32_click_counter%20Installation.md)

# 4. ESP32_click_counter Installation

## 1. Source file copy

There is one directory in the setup file:

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

## 2. Arduino IDE

If Arduino IDE is not installed, download and install

- <https://www.arduino.cc/en/software>

In the directory `C:\YIC\ESP32_click_counter\`, double lick on `ESP32_click_counter.ino` to open Arduino IDE.

Inside Arduino IDE, all files should be present as tabs.

### 2.1. Install ESP32 board

Open the Boards Manager by one of the two ways:

1. On the menu:\
   Tools > Board > Boards Manager... (Ctrl-Shift-B)
2. On the left vertical toolbar of Arduino IDE, press the second button

Boards Manager pane will open between the left vertical toolbar and the code editor.

On top of the Boards Manager, in the textbox "Filter your search...", type in `esp32`. Two or more items will appear.

Install `esp32 by Espressif Systems`

On the menu, select:\
Tools > Board > esp32 > ESP32 Dev Module

### 2.2. Install Vector library

Open the Library Manager by one of the two ways:

1. On the menu:\
  Tools > Manage Libraries... (Ctrl-Shift-I)
2. On the left vertical toolbar of Arduino IDE, press the third button

Library Manager pane will open between the left vertical toolbar and the code editor.

On top of the Library Manager, in the textbox "Filter your search...", type in `vector`. Several items will appear.

Install `Vector by Peter Polidoro`

[![Left Arrow](https://github.githubassets.com/images/icons/emoji/unicode/2b05.png?v8)](3%20ClickCounter%20User%20Guide.md)\
[Previous: 3. ClickCounter User Guide](3%20ClickCounter%20User%20Guide.md)

[![Right Arrow](https://github.githubassets.com/images/icons/emoji/unicode/27a1.png?v8)](5%20ESP32_click_counter%20User%20Guide.md)\
[Next: 5. ESP32_click_counter User Guide](5%20ESP32_click_counter%20User%20Guide.md)

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Main](../README.md)
