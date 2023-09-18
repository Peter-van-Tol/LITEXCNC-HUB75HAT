==========
Connectors
==========

Connector locations
===================


Power
=====


I/O Connector pinout
====================
Three 26 pin header connectors with standard parallel port pinouts and 5V tolerant 
I/O are provided for compatibility with most parallel port interfaced motion control / 
CNC breakout cards / multi axis step motor drives.

.. note::
    The FPGA used on the 5a-75B has a 3.3V absolute maximum input voltage specification. 
    To allow interfacing with 5V inputs, the HUB75HAT has bus switches on all I/O pins
    to provide 5V tolerance (`SN74CB3T3245 <https://www.ti.com/product/SN74CB3T3245>`_).

    Note that even though the HUB75HAT can tolerate 5V signal inputs, its outputs will not
    swing to 5V. The outputs are push pull CMOS that will drive to the output supply rail of
    3.3V. This is sufficient for TTL compatibility but may cause problems with some types of
    loads. For example when driving an LED that has its anode connected to 5V, in such
    devices as OPTO isolators and I/O module rack SSRs, the 3.3V high level may not
    completely turn the LED off. To avoid this problem, either drive loads that are ground
    referred, Use 3.3V as the VCC for VCC referred loads, or use open drain mode.

.. warning::
    After power-up or system reset and before the FPGA is configured, the per connector
    pull-up or pull-down resistors will pull all I/O signals per connector to a high or 
    low level. If the FPGA is used for motion control or controlling devices that could 
    present a hazard when enabled, external circuitry should be designed so that this 
    initial state results in a safe condition.

.. csv-table:: Connector I/O-1
   :file: ./tables/IO1.csv
   :widths: 12, 12, 12, 12, 4, 12, 12, 12, 12 
   :header-rows: 1

.. csv-table:: Connector I/O-2
   :file: ./tables/IO2.csv
   :widths: 12, 12, 12, 12, 4, 12, 12, 12, 12 
   :header-rows: 1

.. csv-table:: Connector I/O-3
   :file: ./tables/IO3.csv
   :widths: 12, 12, 12, 12, 4, 12, 12, 12, 12 
   :header-rows: 1

