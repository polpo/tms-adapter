# TMS9118 to TMS9128 Adapter #

This is a PCB that will let you plug a TMS9128 VDP, along with a [TMS-RGB](https://tms-rgb.com/), into a system that uses a TMS9118 VDP. Such systems include numerous MSX computers.

The adapter is intended to go in the sandwich of: TMS9128 - socket - TMS-RGB - adapter - pin headers - socket - MSX motherboard.

[<img alt="Front and back of board" src="tms-adapter.png" height=400>](tms-adapter.png)

This adapter PCB does the following:

- Moves the TMS9128 CPUCLK signal from pin 37 to pin 38, where it is on the TMS9118.
- Adds 470 ohm load resistors on the Y, R-Y, and B-Y pins as there is no connection to the motherboard on this adapter for those pins. These resistors are required as per the TMS9128 datasheet.

## Rationale ##

I have a Sony HB-101 "HitBit Mezzo" MSX computer that uses the relatively rare TMS9118 VDP. This is the variant that has composite output and supports 16Kx4 video RAM chips. Adding RGB output to systems using these TI VDPs is possible with the TMS-RGB project, but it requires using a VDP with component video output. For systems that use the TMS9118 VDP, a TMS9128 is a close match but the CPUCLK pin is in a different location. My HB-101 requires CPUCLK, so relocating it on this adapter is necessary.

## Making the board ##

Submit the gerbers under the gerbers/ directory to your favorite PCB manufacturer. I made mine at [OSH Park](https://oshpark.com).

A BOM is in the [bom.csv](bom.csv) file, consisting of:

- Low-profile machine pin headers, used to connect this adapter to the socket on the system motherboard
- 40-pin machine pin sockets for the TMS9128 and the system motherboard
- 3x 470 ohm 1% 1/4W 1206 SMT capacitors

TMS9128 chips are available on the used market from eBay, AliExpress, UTSource, etc.

## License ##

[The project license](LICENSE.txt) is under the CERN Open Hardware Licence Version 2 - Permissive.
