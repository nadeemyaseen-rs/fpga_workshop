# fpga_workshop
Day 1 lecture 1.1:
An FPGA is a Field Programmabe Gate Array. It's main advantage over ASIC (Application specific integrated circuit) is that it's hardware can be re-configured as many time as we want as compared to ASIC in which the hardware once defined become permanet and can't be re-configured without repeating the entite cycle. An FPGA architecture has:
* CLB (configureable logic block)
* Programmable interconnection
* I/O
* Configuration memory (bitstream is loaded in it)
* Clock Tiles
* SRAM/memory block
* DSP
* Multiplier

A CLB further consist of:
* LUT (look up table)
* Carry Chain
* Mux
* FlipFlop

LUT:

The desired design like 2 into 1 Mux is can be implemented using the LUT has shown in below screen shot. The possible input of 2 into 1 Mux are 8 which are now input of 3 input LUT. Similarly inter-connection can be use to pass the signal between I/O and LUT and between the LUTs and LUTs. I/Os can programmed to work as input as well as output.

FPGA Design Methodology:

Below diagram shows all the steps involved in implementing a design on FPGA





