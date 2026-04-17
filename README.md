# smart-fan-controller-pcb

Title:
Smart Fan Controller PCB (Temperature-Based PWM System)


Overview:

This project is a custom-designed PCB that controls a 12V fan based on temperature using a microcontroller and PWM control. The system integrates analog sensing, power electronics, and embedded control into a single board.

Features:
Temperature-based fan speed control
PWM motor driving using MOSFET
12V power input with regulated 5V logic rail
Manual control via potentiometer
ISP programming header for firmware upload
System Architecture

Temperature sensor → Microcontroller → PWM → MOSFET → Fan

PCB Design:
2-layer PCB design
Separated power and signal zones
Ground plane for noise reduction
Optimized trace widths for power handling
Design Improvements (V2)
Added LED indicators (power + fan status)
Added ISP programming header
Improved grounding and routing
Better component placement for noise isolation

Tools Used:
KiCad for schematic and PCB design

Files:
Schematic
PCB layout
Gerber files
3D renders

Author:
Larbi Mohamed Redha
