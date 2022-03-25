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

![LUT Examle](screenshots/lut_example_mux.png)

FPGA Design Methodology:

Below diagram shows all the steps involved in implementing a design on FPGA

![methodology](screenshots/fpga_methodolgy.png)

For the Lab we will be using Basys3 board. Below figure shows the different part of this board:

![basys3](screenshots/basys3_board.png)

To download the Software and board related files go to sub-module directory and see slide no. 19

Day 1 Lab:

Vivado Tutorial:

* Invoke vivado

Creating New Project:

* On first screen:
    * click on create new project
    * give project name
    * set the project working directory
    * click next
* Set the board. If the board files are installed then just you can search it using board name other wise select appropriate category then board number to specify the board. Click next
* On left side there is window of `project summary`
* On right side there is window of `project management`

Adding RTL and Testbench:

* To add the RTL files, click on `Add Source` in `project management` window. This will pop up new window, choose `Add or create design source` option and cick next. Point it to RTL files and click `add`. Make sure to choose all the option. Click finish. Under Project Management Window on right side, there is source window, the added files will appera there.
* Follow the above step to add test bench but make sure to select `add or create simulation source` this time.

Running Simulation:

* To run the simulation, click on `Run Simulation` in `Flow Navigator` window on right side. 
Following waveform can be observed in simulation:

![day1_lab_sim_waveform](screenshots/day_1_sim_waveform.png)

Elaborating Design:

To elaborate the design, click on `Open Elaborated Design` in Flow Navigator window. Once the elaboration is done, click on schematic to view how the design is implemented. For the current counter design, schematic looks like as shown below:

![day1_lab_schematic](screenshots/day1_lab_schematic.png)

Similary on top right corner there is box to change the view. Set it to I/O Planning to see the I/O of board as shown in below fig:

![day1_lab_io_plan](screenshots/day1_lab_io.png)

To map the I/O, either look at the data sheet of board or on actual board to find the pin number. On Vivado software, set the clock, reset button and output LEDs. Save it as constraint file. 
Slack means the time difference between the data required time and data arrival time.

Synthesis:

In Flow Navigator window, click on synthesis to synthesis the design. This will synthesis the design. Looking at the timing report indicate us it is not reporting the slack value. That's because we have not given it the clock frequency. To add actual timing we need to provide the clock frequency which can be done using the `Constraints Wizard` in Flow Navigator or using the TCL command in XDC file. Once providing the clock frequency, synthesis the design again. After this, synthesising it again, the schematic will look like as shown below:



Now looking at timing report, it will show us that slack is positive. So we can move to implementation and then generate the bitstream. 




