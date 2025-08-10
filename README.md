# Overview
The Ti AMC33xx are differential isolated analog amplifiers rated for minimum 1.2kVrms insulation. The AMC3302 is intended for current shunt inputs as it has a +/-50mVpp input with a fixed gain of 41, whereas the AMC3330 is better for voltage measurements as it has a +/-1Vpp input and a fixed gain of 2. In these probes the AMC33xx do all the work, with their differential output converted to single-ended by a dual op-amp to better suit most oscilloscopes. 
By using two 2.54" jumpers on the 2x10 header, you can select between various input attenuators for low to high voltage use. 

# Design Notes
The power supply must be isolated from your scope as the scope "GND" of the SMA connector is a 50%VDD bias voltage. 
The schematic has two modifications from the rev A to rev A2 design - refer to the rev B schematic and follow the notes. The modifications are:
- Two biasing 1M (AMC3300) or 100k (AMC3302) resistors from near the input selector to HGND
- Two filtering 33pF (AMC3300) or 3.3nF (AMC3302) capacitors from near the input selector to HGND
- General note: The PCB is marked with an fc of the input circuit, not of the complete probe. The fc of the complete probe is about 300kHz.

The design was originally done in Altium and then converted to KiCad so appologies that the KiCad sch/pcb may not link up quite right. For that reason there are no propper rev B output files, and also note the rev B PCB still has outstanding changes as noted on the schematic.

Other opamps with GBWP >1MHz or so should perform similarly, the OPA2376 is just what was on hand.
Based on practical usage, the AMC3302 with a 0R01 shunt works best for currents >=3mA with fc=100kHz. The AMC3330 on 1:1 range works best for voltages >=10mV and fc=300kHz.

# Disclaimer
Only use the high voltage inputs if you are suitably qualified to measure lethal voltages and completely understand the risks. This project is provided as reference material only and anyone who attempts to make it must fully understand the risks and limitations of the isolator used - this project has absolutely no warranty and may be completely unsuitable for your use case. Use completely at your own risk!
