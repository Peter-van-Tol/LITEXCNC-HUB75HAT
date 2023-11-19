# HUB75HAT

A PCB that turns the Colorlight 5A-75B into an easy to use CNC contorller for cheap.

This project ist based on:
- [cyber-murmel/chubby-hat](https://github.com/cyber-murmel/chubby-hat)
- [3k/chubby75](https://github.com/q3k/chubby75/tree/master/5a-75b])

The HUB75HAT is 5A-75B motherboard host for a Raspberry Pi CPU. The HUB75HAT connects to the RPI’s GPIO interface and uses SPI for FPGA communication. Three 26 pin header connectors with standard parallel port pinouts and 5V tolerant I/O are provided for compatibility with most parallel port interfaced motion control / CNC breakout cards / multi axis step motor drives.

In addition to the parallel expansion ports, the HUB75HAT provides two RS-485 interfaces for I/O communication to other RS-485 applications, such as the Huanyang VFD series. These RS-485 are directly taken from the RPI’s header (UART0 and UART1).

The firmware is flashed onto the 5A-75B by using the RPI’s GPIO pins. There is no need for external programmers.

The motherboard can also be used _without_ the RPI, by using the standard ethernet communication of the 5A-75B. In this case one would loose the ability to use the RS-485 interfaces and an external tool will be required to flash new firmware.

## Version 1.0

The board features:
- Designed for Raspberry Pi 4 and 5 (the older version RPi 3 might also work) with SPI communication
- 3 I/O connectors:
  - each 17 pins of freely addressable inputs / outputs;
  - selectable 10 kOhm pull-down or pull-up resistor;
  - optional 5V power supply on the connector;
- 2 RS-485 connectors for external communications (based on UART0 and UART5 on the Raspberry Pi)

![HUB75HAT](/images/HUB75HAT-v1.0.jpg)

Known issues:
- the space around the 40 pin connector of the HAT is a bit tight with the mounting points of the RPi. The solution to work with the current board is to use plastic stand-offs and cut part of these away.
- the enable signal should be inverted on the board, because the buffer Output Enable (`OE`) is active LOW. I rather send a HIGH signal to the board to enable it (safety).
- enable LED is not working (can also be a problem with the buffer IC, had some trouble with soldering this buffer). However, even if this LED was working, it would indicate that the board would be disabled (see previous point);
- The 3 I/O headers do not have space for shrouded headers. Instead, I chose to use coloured pin headers to show the different functions of the pins;

## Version 1.1

The board features:
- Designed for Raspberry Pi 4 and 5 (the older version RPi 3 might also work) with SPI communication
- 3 I/O connectors:
  - each 17 pins of freely addressable inputs / outputs;
  - selectable 10 kOhm pull-down or pull-up resistor;
  - optional 5V power supply on the connector;
- 2 RS-485 connectors for external communications (based on UART0 and UART5 on the Raspberry Pi);
- Resolved issues of board v1.0;
- re-designed with most of the components on the bottom side of the board. This makes the board cheaper to
  produce with services such as JLCPCB. The final iteration of the board can be ordered assembled starting
  around 15 Eur per piece (excluding shipping, based on the minimum order size of 5 boards.)

## KiCad Version
The following version of KiCad has been used to design the board:
```
Application: KiCad x64 on x64
Version: 7.0.7, release build
Libraries:
    wxWidgets 3.2.2
    FreeType 2.12.1
    HarfBuzz 6.0.0
    FontConfig 2.14.1
    libcurl/7.88.1-DEV Schannel zlib/1.2.13

Platform: Windows 10 (build 19044), 64-bit edition, 64 bit, Little endian, wxMSW

Build Info:
    Date: Aug 19 2023 13:12:00
    wxWidgets: 3.2.2 (wchar_t,wx containers)
    Boost: 1.81.0
    OCC: 7.7.1
    Curl: 7.88.1-DEV
    ngspice: 40
    Compiler: Visual C++ 1936 without C++ ABI

Build settings:
    KICAD_SPICE=ON
```
