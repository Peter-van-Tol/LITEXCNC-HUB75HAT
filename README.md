# HUB75HAT

A PCB that turns the Colorlight 5A-75B into an easy to use CNC controller for cheap.

This project ist based on:
- [cyber-murmel/chubby-hat](https://github.com/cyber-murmel/chubby-hat)
- [3k/chubby75](https://github.com/q3k/chubby75/tree/master/5a-75b])

The [HUB75HAT](src/HUB75HAT) is 5A-75B motherboard host for a Raspberry Pi CPU. The HUB75HAT connects to the RPI’s GPIO interface and uses SPI for FPGA communication. Three 26 pin header connectors with standard parallel port pinouts and 5V tolerant I/O are provided for compatibility with most parallel port interfaced motion control / CNC breakout cards / multi axis step motor drives.

In addition to the parallel expansion ports, the HUB75HAT provides two RS-485 interfaces for I/O communication to other RS-485 applications, such as the Huanyang VFD series. These RS-485 are directly taken from the RPI’s header (UART0/1 and UART5).

The firmware is flashed onto the 5A-75B by using the RPI’s GPIO pins. There is no need for external programmers.

The motherboard can also be used _without_ the RPI, by using the standard ethernet communication of the 5A-75B. In this case one would loose the ability to use the RS-485 interfaces and an external tool will be required to flash new firmware.

## Breakout boards (BOB)
Breakout boards are available for the HUB75HAT. These BOBs are designed to add functionality to the HUB75HAT by
extending the GPIO from the 3 26 pin header connectors with drivers, receivers, opto-couplers, etc. Currently the
following BOBs are available:
- [BOB4AXIS](src/BOB4AXIS): Supports driving of 4 axis with differential output. Has inputs for the ALARM of the stepper
  drivers for each axis. Also has optocouplers for homing switches. The homing switches can be either NPN or PNP (selectable
  per axis). Adding this BOB would be enough to run a small 3 axis CNC machine with 1 slave axis.
- [BOB4ENCODER](src/BOB4ENCODER): Supports up to 4 encoders with index (5V only). Unused inputs can be used for generic
  IO. This board also has two connections for SERIAL boards, to further expand GPIO for your machine.

## Serial boards (SERIAL)
These boards are still under development. Goal is to extend GPIO with SPI expanders.

## Releases
The table below gives for each board the current status and the latest release. 

| board               | latest release                           |
|---------------------|------------------------------------------|
| HUB75HAT            | [v1.1](src/HUB75HAT/releases/v1.1/)      |
| BOB4AXIS            | [v1.1](src/BOB4AXIS/releases/v1.1/)      |
| BOB4ENCODER         | [v1.0](src/BOB4ENCODER/releases/v1.0/)   |

In each release folder you'll find a production folder with:
- a .zip-file which can be uploaded to your favorite PCB manufacturer
- a BOM;
- a position file for assembly (only verified for HUB75HAT, the rest is hand-soldered)

## KiCad Version
The following version of KiCad has been used to design the boards:
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
