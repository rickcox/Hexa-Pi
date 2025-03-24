# Hexa-Pi
A Compact 6 Compute Module Cluster

This is a PCB based project to create a very compact cluster of
Raspberry Pi CM4 compatible compute module boards.  It is quite bare-bones
in terms of peripheral support.  One of the modules - Module 5 - has a basic set of peripherals.
The other Modules - 0-4 - have only a small external connector for all I/O.
All 6 modules attach to a 1Gbit ethernet switch IC, which also has 2 off-board connectors.

It should be emphasized that **Compact Compute Cluster** is the focus of this design, not connectivity.
Connectivity, and peripheral support, has been reduced to meet the compact compute cluster goal.
Since all low voltage power, and the ethernet switch are on-board, a cluster of 6 Compute modules
can be supported with 1 12V DC power jack and 1 ethernet cable.
A 6 amp or larger 12V supply is recommended to support 6 running modules.

In addition, there are 2 external ethernet switch connectors, allowing boards to be "daisy chained".

![A simple overview](Hexa-Pi_PCB/doc/Hexa-Pi_Summary.png)


The PCB is 150mm X 150mm X 1.6mm.  

![A View of the Hexa-Pi Board with 6 Pi CM4's installed](Hexa-Pi_PCB/doc/Hexa-Pi_1.1_TOP-ALL.png)

A goal of this design is to be as Compute Module independent as possible, to allow
for a variety of compatible modules to be used.  Several of the Compute Module compatible
boards have been tested:

- ![Raspberry Pi Compute Module 4: ](https://www.raspberrypi.com/products/compute-module-4)
  This board basically defigned the standard, so everything possible works on a Pi CM4.
  CM4 boards in the Module5 location may be either "Lite" or with EMMC.
  CM4 boards in the Module0-4 locations must have EMMC.
  
- ![Pine64 SOQuartz: ](https://pine64.org/documentation/SOQuartz)
  This RK3566 base board works well. 
  Rockchip processors for some odd reason must use 1.5Mbps on the serial console.  
  The pluggable EMMC modules makes setup of these boards very easy if you buy a cheap EMMC-microSD converter.

- ![Banana Pi CM4: ](https://www.banana-pi.org/en/core-board-and-kit/129.html)
  This Amlogic A311D based board is a bit faster than the Raspberry Pi CM4.
  These are a bit fussy to get setup, and OS selection is quite limited.

- ![Radxa CM5: ](https://radxa.com/products/cm/cm5)
  This RK3588 based board is **very** fast, if that is what you are looking for.
  There are "Lite" and "Full" versions of this board. Only he Full has been tested, but both should work.
  Use caution that the extra 3rd connector does not make contact with the Hexa-Pi PCB components.
  Again, Rockchip processors use 1.5Mbps on the serial console.
  OS selection is also limited here.
  Due to higher power consumption, a larger heatsink is recommended for the Radxa CM5.

- ![Raspberry Pi Compute Module 5: ](https://www.raspberrypi.com/products/compute-module-4)
  **Testing TBD.**
  Not sure if serial port will work.
  The CM5 fan support is not compatible with CM4 or Hexa-Pi. The I2C fan controller can be used,
  as with a CM4

- Due to higher power consumption, a larger heatsink and possibly a heatspreader is recommended for the Raspberry Pi CM5.

Not all "compatible" boards have been tested.  
It is expected, unless the manufacturer has done something specific to make it incompatible, most "compatible" boards should work. 
Reviewing the datasheet and pinout on the 100 pin mezzanine connectors can be useful in spotting incompatibilities.

The Raspberry Pi CM4 boards have been most throughly tested.  
The other boards all have been verified to operate and connect via etherent, but all of the ports have not been tested.
Where known, incompatibilities have been noted.
It is recommended to initially configure an unfamiliar Compute Module in a Raspberry Pi CM4 IO board,
or board vendor specific baseboard, where all of the IO ports are available.
The Module5 location on the Hexa-Pi board may work for this, since it has USB, HDMI, and microSD
card support - but does not have the 40pin IO connector. 
Having a GUI is often helpful for the initial OS setup on a new board - even if your eventual use is headless.

Also, there is a small "Pi-Panel" support board that attaches to the external connectors 
at the top to provide a few simple peripherals for **all** of the Modules individually. 
A Green activity LED for each module is visible at the top, next to that module's connector.

There are also a Red power LED, a Yellow USB Overload LED, a White rpibboot mode LED, and a Blue NVME activity LED,
all on the main PCB, bottom edge.

Also included is stl files for a case for the Hexa-Pi board.
The PCB's were built, and mostly assembled, by JLCPCB.
The Case was 3D Printed. 

There is more information in the sub-directories:

- ![Main Hexa-Pi PCB](Hexa-Pi_PCB/README.md)
- ![Case for Hexa-Pi](Hexa-Pi_Case/README.md)
- ![Pi-Panel PCB](Pi-Panel_PCB/README.md)

This work is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of the license, visit https://creativecommons.org/licenses/by/4.0/
