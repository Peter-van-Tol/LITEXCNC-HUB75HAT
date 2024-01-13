=========
CHANGELOG
=========

Version 1.2 (current version)
=============================

During soldering the version 1.1 boards, the following issues have been identified and solved in this version:
- The 40-pin header has the wrong footprint, there fore it clashes in practice with two polyfuses. The footprint
  will be corrected and the polyfuses will be moved to make space for the 40-pin header.
- Several markings on the board are missing. These will be added to the board.
- Removed unused diode from the board.

Version 1.1
===========

First production version of the board. In total 15 boards were ordered from JLCPCB. The boards were assembled by JLCPCB as well.
The total cost per board was around €17.50 (including shipping and taxes).

The board features:
- Designed for Raspberry Pi 4 and 5 (the older version RPi 3 might also work) with SPI communication
- 3 I/O connectors:
  - each 17 pins of freely addressable inputs / outputs;
  - selectable 10 kOhm pull-down or pull-up resistor;
  - optional 5V power supply on the connector;
- 2 RS-485 connectors for external communications (based on UART0 and UART5 on the Raspberry Pi);
- Resolved issues of board v1.0;
- re-designed with most of the components on the bottom side of the board. This makes the board cheaper to
  produce with services such as JLCPCB. The components to be soldered by hand are on the top side of the board,
  and are limited to: 6 LED's (size 1206), 7 polyfuses (size 1812) and the connectors. 


Version 1.0
===========

Initial version of the board. 

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
