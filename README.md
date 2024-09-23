FPGA-based RF Signal Generation and Modulation

Project Overview
This project focuses on the generation and modulation of RF signals using an FPGA. 
The design is implemented using various IP cores such as BRAM, DDS, and a Complex Multiplier. 
The primary aim is to generate RF signals of the form cos(wt + mt) by integrating different components within an FPGA design flow.

Features
DDS Compiler: Generates carrier signals (cos(wt) and sin(wt)) at different frequencies.
BRAM IP Core: Stores pre-calculated values for modulating signals (cos(mt) and sin(mt)).
Complex Multiplier: Multiplies the modulating and carrier signals to create a mixed RF signal.
Adder/Subtractor: Combines the real and imaginary parts to generate the final RF waveform.
Clock Signals: Utilizes a 160 MHz clock for synchronized operations.

Getting Started

Prerequisites
MATLAB and Xilinx Vivado Design Suite (tested with version 2021.1)
Basic understanding of Matlab, Verilog HDL, FPGA, and RF signal generation

Step 1: Generate .coe File from MATLAB
Prepare Data:

Create your data set in MATLAB, which could be a sequence of values (e.g., coefficients for your RF signal modulation).
Format Data:

Ensure the data is in the correct format for your application. For a BRAM, the values should be in hexadecimal format.
Export to .coe:

Use MATLAB functions to write the data to a .coe file. The file should follow the specific format required by the BRAM IP core in Vivado, including headers and data sections.
Step 2: Integrate .coe File into Vivado IP Integration
Open Vivado:

Launch Xilinx Vivado and create a new project or open an existing one.
Add IP Core:

Navigate to the IP Catalog and add the Block Memory Generator (BRAM) IP core to your design.
Configure BRAM:

In the BRAM configuration settings, choose "Dual Port" or "Single Port" mode as needed.
Under the "Initialization" options, select "Load Memory from File" and point to your .coe file.
Set Data Width and Depth:

Configure the width and depth of the BRAM according to your design requirements.
Connect IP Cores:

Connect the BRAM output to the necessary components in your design (e.g., complex multipliers or adders).
Step 3: Simulation
Create Testbench:

Develop a testbench to verify the functionality of the integrated design. This includes stimulating the inputs and observing the outputs.
Run Simulation:

Execute the simulation in Vivado to check if the BRAM correctly loads data from the .coe file and interfaces properly with other IP cores.
Analyze Results:

Use the waveform viewer to validate the expected outputs and ensure proper data flow through the system.
Step 4: Synthesis
Synthesize the Design:

After successful simulation, proceed to synthesize the design. This step checks for logic errors and prepares the design for implementation.
Review Synthesis Report:

Check for any warnings or errors in the synthesis report. Ensure that timing constraints are met.
Step 5: Implementation and Bitstream Generation
Implement the Design:

After synthesis, implement the design. This step maps the synthesized design onto the physical FPGA resources.
Generate Bitstream:

Once implementation is complete, generate the bitstream file. This file contains the configuration data needed to program the FPGA.
Program the FPGA:

Use the generated bitstream to program the FPGA for testing in real hardware.
Summary
Following these steps will enable you to generate a .coe file from MATLAB, integrate it into your FPGA design in Vivado,
and successfully simulate, synthesize, and generate a bitstream for implementation.
