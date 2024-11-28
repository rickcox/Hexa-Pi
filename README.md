# Hexa-Pi
A Compact 6 Compute Module Cluster

This is a PCB based project to create a very compact cluster of
Raspberry Pi CM4 compatible compute boards.  It is quite bare-bones
in terms of peripheral support.  One of the modules - Module 5 has a basic set
of USB, HDMI, micro SD, a pcie SSD, a USBC port for flashing a Pi's EMMC, and a fan control chip.  
The other Modules, 0-4, have only a small external connector for I/O.
All 6 modules attach to a 1Gbit ethernet switch IC, which also connects off-board.
The entire board - 6 compute modules, switch, and misc functions are powered off of
a single 12V barrel Jack. Oh, and all 6 Modules have an activity LED.

Also,there is a small "Pi-Panel" board that attaches externally to provide a few
simple peripherals for each Module separately: 
- A Reset switch
- An external Serial console 
- A USB port usable as a USB drive
- An I2C bus and QWIIC or Stemma-QT style connectors

The PCB is 150mm X 150mm.  
Also included is a 3d printable case for the Hexa-Pi board and Pi-Panel.

