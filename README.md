# FabLabRocker

A simple servo-based lab rocker with variable frequency and amplitude.
Designed for DIY PCB fabrication, but can be used for large format photography or chemistry.
3d-design is customizable, written in OpenSCAD and BOSL2.
Measure your container and make the parts that fit ideally.

## PCB

PCB is as simple as it can get.
The project is all about DIY PCB fabrication, so of course it is.
It is one-sided and basically connects a ready-made modules.
Power from a cell does through a switch to DC-DC converter that powers Arduino and the servo.
Two potentiometers are wired to 0 and 5v rails and to analog inputs of Arduino.

### Parts list

TODO: write down particular parts used

- Arduino Nano or Pro Micro
- 2 linear Potentiometers, about 25k or more
- DC-DC converter
- 18650 holder
- Pin headers
- Switch
- Servo
- 3d-printed parts

## 3d-printed parts

Model parameters are grouped into self-explanatory categories.
most important are ```bath_width```, ```bath_depth``` which are measurements of container bottom, and ```bath_rounding``` and ```bath_chamfer```, which define corner rounding of the container.
Of the last two parameters only one can be non-zero.
Print as is, for the ```top_mech``` part use organic supports.

## Assembly

Assemble the PCB.
KiCad project is in ```agitator_pcb```.
Don't forget to set the voltage of DC-DC converter to 5v.
Customize the mechanical parts and print them.
The moveable joints are formed by two M4x8 screws.
For the top assembly use 4 thread inserts in ```top_mech```, for mounting the motor use 2 in ```bottom``` and matching M2x8 screws.
Or don't. You can use self-tapping screws or glue or whatever.
PCB is held by the pots.

### Usage

One pot changes the oscillation frequency, the other controls amplitude.
High amplitudes are not achievable with high frequencies.
If the servo does not have time to rotate to the goal position it will never achieve the amplitude.