=================
LITEXCNC-HUB75HAT
=================

A PCB that turns the Colorlight 5A-75B into an easy to use CNC motion controller for cheap. This 
project is based on `q3k/chubby75 <https://github.com/q3k/chubby75/tree/master/5a-75b>`_ and 
`LitexCNC <https://github.com/Peter-van-Tol/LiteX-CNC>`_.

The HUB75HAT is 5A-75B motherboard host for a Raspberry Pi CPU. The HUB75HAT connects to the RPI's
GPIO interface and uses SPI for FPGA communication. Three 26 pin header connectors with standard
parallel port pinouts and 5V tolerant I/O are provided for compatibility with most parallel port 
interfaced motion control / CNC breakout cards / multi axis step motor drives.

In addition to the parallel expansion ports, the HUB75HAT provides two RS-485 interfaces for I/O 
communication to other RS-485 applications, such as the Huanyang VFD series. These RS-485 are directly
taken from the RPI's header (UART0 and UART1).

The firmware is flashed onto the 5A-75B by using the RPI's GPIO pins. There is no need for external
programmers. 

The motherboard can also be used *without* the RPI, by using the standard ethernet communication
of the 5A-75B. In this case one would loose the ability to use the RS-485 interfaces and an external
tool will be required to flash new firmware. 

Contents
========

.. toctree::
   :maxdepth: 2

   Connectors <connectors>
   Status LEDs <status_LEDs>
   Preparing your 5A-75B <5a-75b>
   Preparing your Raspberry-Pi <rpi>
   License <license>
   Changelog <changelog>

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
