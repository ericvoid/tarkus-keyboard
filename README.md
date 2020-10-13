# Tarkus Keyboard

A handwired keyboard inspired on [Helix Keyboard](https://github.com/MakotoKurauchi/helix)
and on Xah Lee's [No Chord Keyboard](http://xahlee.info/comp/ultimate_keyboard_layout.html).
It uses the Arduino Micro (not Pro Micro) and is programmed with the QMK Framework.

![Photo](media/picture.png)

## Layout

The keyboard has the following modes: the Standard mode and the Programmer mode.

In the Standard mode, the keyboard works just as expected. Currently, it is
programmed with the Dvorak layout.

In the Programmer mode the keys on the numeric row are replaced with symbols,
reducing the need of using the Shift modifier.

In addition, there is the Numpad layer, that can me momentarily activated.

## Build Guide

Bill of materials:

* 1x Acrylic case 92x Cherry MX switches, or compatibe;
* 1x [Arduino Micro](https://store.arduino.cc/usa/arduino-micro) or compatible (it is not a Pro Micro);
* 8x M3 screws (the legnth depends on the tickness of the case);
* 4x M3 screws (the length depends on the height of the foot);
* 12x M3 nuts; 1x 0.91" Oled display (128x32 px);
* 92x diodes;
* wires, soldering tin, soldering iron.

The default *acrylic case* is composed of the following parts:

* switch plate - 1x 3mm;
* spacer - 4x 3mm (or 2x 6mm);
* bottom plate - 1x 3mm;
* foot - 1x 3mm.

If you make the spacers with total height of 12mm, you have plenty of space to
do the wiring inside. And since the keyboard is quite wide, it won't look very
thick.

The foot is optional, and it can be attached to the bottom plate. Since it is
made of layers, it is possible to raise or lower the feet by adding or removing
them. Be warry of the m3 screws for the feet, you should also account the
thickness of the bottom plate.

![Wiring Diagram](media/wires.png)

![Photo](media/diodes.png)

The odd connections at the middle column also should have similar diode
connections, the dioeds should be between the switch pin and the row, with the
marked end (cathode) pointing to the row line.

![Oled](media/oled.png)

Some oled display modules comes with the SCL pin labeled as SCK - in this case
it also should be wired to 3/SCL/PD0.

## Flashing the Firmware

Currently the firmware is not available by default in the QMK repository.

To flash the firmware, copy the contents of the `src` directory of this repo
to `~/qmk_firmwarke/keyboards/handwired/tarkus`. Then compile running:

    qmk compile -kb handwired/tarkus -km default

And flash it running:

    qmk compile -kb handwired/tarkus -km default
