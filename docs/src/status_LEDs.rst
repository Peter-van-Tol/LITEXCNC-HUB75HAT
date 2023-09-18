===========
Status LEDs
===========

LED locations
=============

The board has three groups of status LEDs:

#. Power, ENA and ESTOP;
#. TX/RX for RS-489 connnection 0 (UART0)
#. TX/RX for RS-489 connnection 1 (UART1)


Power, ENA and ESTOP
====================
The power indicator is on when power is supplied to the HUB75HAT (either by the RPi or the
5A-75B). When this LED is on, **DO NOT** unplug the GPIO connector, as this may lead to 
irreversible damage to the RPi and/or 5A-75B.

The ENA indicator is on when the board got the _enable_ command from LinuxCNC. When this LED 
is on, signals from the 5A-75B will flow to the three I/O connectors. It is strongly recommended
not to change connections from the I/O, as this may result in damage or unexpected movement of
the machine.

The ESTOP indicator can only be on when the machine is enabled. It is turned on when any 
ENA/ESTOP pin (pin 1 on the I/O connectors) is pulled to ground. LinuxCNC will disable the
machine when the ESTOP has been triggered. Therefore, the LED is latched until the machine
is enabled again.

TX/RX status LEDs
=================
Both RS-489 connectors have two LEDs indicating communication to and from the port.
