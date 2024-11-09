# Overview
The Ti AMC33xx are differential isolated analog amplifiers rated for minimum 1.2kVrms insulation. The AMC3302 is intended for current shunt inputs as it has a +/-50mVpp input with a fixed gain of 41, whereas the AMC3330 is better for voltage measurements as it has a +/-1Vpp input and a fixed gain of 2. In these probes the AMC33xx do all the work, with their differential output converted to single-ended by a dual op-amp to better suit most oscilloscopes. 
By using two 2.54" jumpers on the 2x10 header, you can select between various input attenuators for low to high voltage use. 

# Design Notes
The power supply must be isolated from your scope as the scope "GND" of the SMA connector is a 50%VDD bias voltage. 
The schematic has 3 modifications from the rev A to rev A1 design - a Y1 capacitor and two 1M biasing resistors - see schematic/PCB for location.
The design was originally done in Altium and then converted to KiCad so appologies that the KiCad sch/pcb may not link up quite right.
The PCB is marked with an fc of the input circuit, not of the complete probe. The fc of the complete probe is about 300kHz and details can be found in the AMC3330/AMC3302 datasheet.
Other opamps with GBWP >1MHz or so should perform similarly, the OPA2376 is just what was on hand.
Based on practical usage, the AMC3302 with a 0R01 shunt works best for currents >=3mA with fc=100kHz. The AMC3330 on 1:1 range works best for voltages >=10mV and fc=300kHz.

# Disclaimer
Only use the high voltage inputs if you are suitably qualified to measure lethal voltages and completely understand the risks. This project is provided as reference material only and anyone who attempts to make it must fully understand the risks and limitations of the isolator used - this project has absolutely no warranty and may be completely unsuitable for your use case. Use completely at your own risk!
