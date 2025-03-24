# Pi-Panel
A small "Front Panel" for the compute modules in the Hexa-Pi PCB.
5 of the modules have no other peripherals other than ethernet.

![the Pi-Panel PCB](doc/Pi-Panel_1.1.jpg)

This is a small 36mm X 50mm PCB based that connects to the main Hexa-Pi board
using a 10 wire interface with JST connectors.

Since the individual Compute Modules on the main PCB are all powered together,
the goal with this board is to allow some basic repair and diagnosis if here are errors 
or failures on specific modules - without powering the main board down and disassembling the case!

The Activity LED for each module is adjacent and to the left of that board's conncetor.
The panel provides for each module individually:
- 5V and Gnd. Realistically about 500ma MAX can be pulled from 5V.
  **Warning** this is NOT current limited. 
  If you overload it, you will undervolt that Compute Module
- A Reset Push-Button for that specific CM.
- A serial console and CH340C USB to serial converter.
  You can directly plug into the USB-C connector and see a serial port.
  This connection uses the Raspberry 4 Compute Module serial interface pins -
  GPIO 14 (RxD) and GPIO 15(RxD). NOTE - some of the non-Raspberry Pi
  Compute modules default to different Serial console ports&pins
- A USB 2.0 port. This may be used to add any normal usb peripheral to the Pi.
  A USB Flash drive is the obvious usage, but anything USB2 compatible should work.
- An I2C port. This can be used for whatever desired.  
  This was initially envisioned as some sort of external display and maybe a couple
  buttons to control it.  Nothing has been developed here though, but
  there may be some interesting off-the-shelf options out there.
  The I2C is available on 3 Pi-Panel connectors:
  - A QWIIC Connector.
  - A Stemma-QT Style connector.
  - 0.1 inch headers.  Included is a 3.3V supply, which may be useful in some situations.
    This is a 250ma LDO off of the 5V supply, so remember the current **warning** above.

The connection to the main Hexa-Pi board uses a 10 pin JST GH 1.25mm connector.
Manufacturer partnumber SM10B-GHS-TB.  It is possible to buy pre-assembeled cables
with this mating connector. They can be purchased with connectors on both ends, or
having 1 end free.  Look for something like "GH 1.25MM 10P Single Ended" or "Double Ended".  
There are solderable holes on the Pi-Panel so the "Single Ended" type cable assemblies can be used,
and hand soldered on the Pi-Panel end.

Oh, and **one ugly secret!** The 10 pin JST connectors used between the Panel and main Hexa-Pi
board do not support any type of sequencing (Connect ground before anything else).
As a result, plugging the Pi-Panel into a running Hexa-Pi **MAY** result in the
connected Compute Module spontaneously resetting.  Being careful to have the Panel
grounded before plugging it in seems to minimize this anomaly!  
If another version of this board is done, this is on the list of things to try and fix, 
but you need to live with it for now.

This was developed in KiCad, and the design files are here.
The initial PCB's were built by JLCPCB, and partially assembled by them.
The through-hole parts and I2C connectors were hand assembled.

This PCB was small enough, that a panel of 2 was actually build.
Directory **production** has the 1 instance manufacturing data, and
directory **production-pnl** has the 2 instance manufacturing data.
At JLCPCB, both PCB's cost the same, since they are under 50mmX50mm.
The assembled 2 instance panel costs slightly more due
to the incremental cost of the parts - but you get 2 boards for the price of 1!

This work is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of the license, visit https://creativecommons.org/licenses/by/4.0/
