> [English](README.en.md) | [Русский](README.md)  
  
# Leningrad-2 128K Modification Guide (Classic Piggyback Method)


This modification allows the stock Leningrad-2 computer to run any official software and games designed for both the \*\*Spectrum 128K\*\* and \*\*Spectrum 48K\*\* models.



## Required Components



In addition to the components specified in the main schematic, you will need:

*   \*\*8x KR565RU5 (КР565РУ5 / 4164)\*\* DRAM chips. \*Crucial:\* They must have the exact same speed/letter suffix rating as the chips already installed on your motherboard.

*   \*\*1x 27256\*\* EPROM chip flashed with the official Spectrum 128K firmware.



\---



## Step-by-Step Assembly



1\.  \*\*RAM Stacking (Piggybacking):\*\* Solder the second set of 8x RU5 DRAM chips directly on top of the original motherboard RAM chips, pin-for-pin. 

&#x20;   \*   \*\*Do not solder pin 15\*\* of the upper chips. Instead, bend pin 15 of all upper chips upward, tie them together with a jumper wire, and connect this line to the \*\*`CAS1`\*\* signal.

&#x20;   \*   Locate pin 15 of the lower (original) RAM row. Cut the original trace feeding them and connect this row to the \*\*`CAS0`\*\* signal.

2\.  \*\*Address Lines:\*\* Disconnect lines `A14` and `A15` from the `D21` multiplexer chip (KR555KP11 / 74ALS257) on the motherboard. Connect the new \*\*`A14+`\*\* and \*\*`A15+`\*\* signals to those freed multiplexer pins respectively.

3\.  \*\*ROM Switch Signal:\*\* Connect the \*\*`CHSR`\*\* signal to pin 13 of the `D24` multiplexer chip (KP11), replacing its original connection to Ground (GND).

4\.  \*\*EPROM Installation:\*\* Replace the stock `D18` ROM chip with your newly flashed 27256 EPROM. Connect the \*\*`A14R`\*\* signal to pin 27 of this EPROM socket.

5\.  \*\*Decoder Modification:\*\* Locate the `D15` decoder chip (KR555ID7 / 74ALS138). Isolate/cut pin 1 from the `A13` address line. Then, pull pin 1 up to \*\*`+5V`\*\* through a \*\*2 kOhm\*\* resistor.



---



## Tuning \& Calibration



Tuning must be performed using a diagnostic \*\*Test ROM\*\* chip. 



The calibration process involves adjusting the propagation delay of the \*\*`RAS`\*\* signal. To achieve full system stability and eliminate RAM artifacts, find the optimal capacitance value by temporarily placing a small ceramic capacitor (typically between 10pF and 100pF) between pin 4 of any RU5 RAM chip and Ground (GND).



