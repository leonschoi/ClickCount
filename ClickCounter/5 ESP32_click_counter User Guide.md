# 5. ESP32_click_counter User Guide

In the directory `C:\YIC\ESP32_click_counter\`, double lick on `ESP32_click_counter.ino` to open Arduino IDE.

ESP32 is used for two tasks

1. Detect switch button press
2. Transmit the press signal to ClickCounter computer

The C++ program variables used by these two tasks are in two files: `config.cpp` and `config.h`.

## Switch button press

For switch button press detection, we need to specify the pin connected to the switch.  It is in `config.h`

```C++
//
// ESO32 pin connection variable
//
const uint8_t pinNumberButton = 27; // pin ID the switch is connected to
```

## Signal transmission

To transmit signal to ClickCounter computer, we need WiFi loginID/password and the host computer name/port.

In `config.h`, two constants are defined.

- `PORT_NUMBER` is the same for all ClickCounter for now.
- `MAX_LOGIN_INFO_SIZE` is used to specify WiFi loginID/password list entry count.

```C++
//
// WiFi and host PC info variables
//
const int PORT_NUMBER = 8201;      // port number used for ClickCount service on Windows
const int MAX_LOGIN_INFO_SIZE = 3; // loginInfoStore array entry count
```

In `config.cpp`

- `HostInfo` type is used to declare a variable that contains host computer name and port number.
- `LoginInfo` array contains a list of WiFi loginID/password and host computer in the network.

```C++
//
// Host computer name and port number
//
HostInfo host1("hostname1", PORT_NUMBER);
HostInfo host2("hostname2", PORT_NUMBER);
HostInfo host3("hostname3", PORT_NUMBER);

//
// WiFi login/pw and ClickCounter host to connect on the network
//
LoginInfo loginInfoStore[MAX_LOGIN_INFO_SIZE] {
  // ssid     password               host
  {"WiFi1",   "enter password here", &host1},
  {"WiFi2",   "enter password here", &host2},
  {"WiFi3",   "enter password here", &host3}
};
```

Note how `MAX_LOGIN_INFO_SIZE` is used above.  It has to match the list entry count.

ESP_click_counter will run through the items of the `loginInfoStore` list, trying to connect for 20 seconds each.

## User specified variables review

In sum, the variables that ___need to be specified by the user___ for both button switch connection and signal transmission are

In `config.h`

```C++
// ESO32 pin connection variable
const uint8_t pinNumberButton = 27; // pin ID the switch is connected to

// WiFi and host PC info variables
const int MAX_LOGIN_INFO_SIZE = 1; // loginInfoStore array entry count
```

`PORT_NUMBER` need not change unless ClickCounter on Windows changes the port assignment.

In `config.cpp`

```C++
// Host computer name and port number
HostInfo host1("hostname1", PORT_NUMBER);

// WiFi login/pw and ClickCounter host to connect on the network
LoginInfo loginInfoStore[MAX_LOGIN_INFO_SIZE] {
  // ssid     password               host
  {"WiFi1",   "enter password here", &host1},
};
```

## Run the program

Connect ESP32 unit to the computer running Arduino IDE.

On the menu, select:\
Tools > Board > esp32 > ESP32 Dev Module\
Tools > Port > COM?

COM? will have a number that the computer has selected.

To open the program output window\
On the menu, select:\
Tools > Serial Monitor (Ctrl-Shift-M)

Compile the program by one of two ways:

1. On the menu:\
   Sketch > Verify/Compile (Ctrl-R)
2. On the top toolbar, click on the first button showing down arrow.

If it compiles, upload the program by one of two ways:

1. On the menu:\
   Sketch > Upload (Ctrl-U)
2. On the top toolbar, click on the second button showing right arrow.

After uploading, the Serial Monitor window will show an output similar to the follwing:

```BASH
01:35:30.331 -> Connecting to WiFi1 network... 0 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 1 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 2 second(s)
01:35:30.331 -> Connecting to WiFi1 network... 3 second(s)
01:35:30.331 -> WiFi connection successful.
01:35:30.331 -> IP address: 10.216.77.137
01:35:30.331 -> Interrupt capture task ESP32 core 1
01:35:30.331 -> TCP send task ESP32 core 0 Serial 246863502882720
```

On each click of the button, the Serial Monitor window will show the click data in the following format

```BASH
01:19:29.777 -> firstTriggerTime 12341292
01:19:29.777 -> lastTriggerTime  12341437
01:19:29.777 -> Data 246863502882720_c1_f12341292_r12341437
```

If the connection to WiFi or host machine fails, it will print the error essage

```BASH
01:19:29.784 -> TCP connection failed hostname1 8201
```

[![Left Arrow](https://github.githubassets.com/images/icons/emoji/unicode/2b05.png?v8)](4%20ESP32_click_counter%20Installation.md)\
[Previous: 4. ESP32_click_counter Installation](4%20ESP32_click_counter%20Installation.md)

[![Anchor](https://github.githubassets.com/images/icons/emoji/unicode/2693.png?v8)](../README.md)\
[Next: Main](../README.md)
