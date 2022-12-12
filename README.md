# pmw3610_breakout

## List of files
- **gerber.zip** : ready for manufacture (recommended PCB thickness: 1 mm)
- **bom.csv and ibom.html** : BOM
- **PMW3610-Ref.kicad_mod** : footprint for keyboard integration (warning: put it on the bottom side)
- **datasheet** : lens datasheet
- **schematics.png**
- **board.png**
- **design/pcb** : the board design file in case you need to modify the outline and add screw holes.

## Build guide
### socket pins
Be aware that the pin hole is only 0.55 mm.
It's designed to be used with low-profile (2.5mm height and 2.54mm pitch) socket.

Some recommendations:
- https://keycapsss.com/keyboard-parts/parts/100/single-row-socket-headers-or-pins-mill-max-series-315
- https://item.taobao.com/item.htm?id=589838076159

### footprint placement
If your trackball is installed on the front side of the pcb, the footprint should be placed on the bottom side.

### optical center selection
There are two optical centors indicated in the footprint:
- for trackballs with diameter larger than 20 mm, use the optical center from datasheet
- for trackballs with diameter smaller than 15 mm, use the 'realistic' one

### RESET soldering jumper
If you wanna actively control the reset using the RESET pin, connect 1-2 of the jumper.
If you do not need RESET control, connect 2-3 of the jumper.
Check **board.png** for the numbering of the jumper.

The [driver implementation](https://github.com/ufan/zmk/tree/ptdevice-refactor/app/drivers/sensor/pixart/pmw3610) in zmk does not use the RESET pin.

## Firmware
I have implemented the driver under a fork of zmk (https://github.com/ufan/zmk/tree/ptdevice-refactor) .
Check [this reference shield](https://github.com/ufan/zmk/tree/ptdevice-refactor/app/boards/shields/blade** for integrating into your keyboard.

## Datasheet
The sensor: https://item.taobao.com/item.htm?id=589838076159
The sheet about the lens can be found under **datasheet**

## PCB Design file
The breakout is extracted from my keyboard project. So the design file is not complete (no schematics design file).
But it should be sufficient to make some outline adjustment and adding extra screw holes.

There are many alternative regulator on the market with compatible footprint. In most cases, it's not necessary to 
change the circuit design.
