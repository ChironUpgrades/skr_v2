# Marling firmware using an Anycubic Chiron upgraded with an SKR 2 motherboard

**HUGE THANKS TO EvilGremlin WHICH DID MOST OF THE WORK** :sparkling_heart:

## SRK MCU

This firmware build is for the newer SKR 2.0 board, they mount the STM32F429 MCU, if you use the STM32F407 you will have to edit the line in platformio.ini (you will have to check to right code to use):
```c
default_envs = BIGTREE_SKR_2_F429 
```

## FIRMWARE

We are currently working on the bugfix Marlin version since in the latest release the STM32F407 MCU has not been implemented yet.

## SENSORLESS HOMING

You will need the TMC2209 stepper drivers, and a BLTOUCH, you will need to make additional changes in case if:
- You have a different hotend mount (you will need to change the probe offset)
- You don't have the TMC2209, you will have to turn off the sensorless homing feature
- You don't have a BLTOUCH, you might still be able to use sensorless homing for the Y and X axis, but you will need to leave the stock z axis end stops.

## Z DOUBLE STEPPER MOTORS

The chiron has 2 Z motors, to move each motor indipendently it's important to use the E1 slot in the motherboard to connect one of the Z stepper motor.
If you use the Z1 slot you will have both motors moving not indipendently.

## TFT

The stock LCD was giving too much problems, the SKR 2.0 doesn't have a beeper pin in the TFT slot meaning the LCD would need a review and additional work which is not worth.
This firmware version works with a BTT TFT35 E3 V3.0 LCD.

## HOTEND/EXTRUDER

This firmware is tuned to work with an Hemera.<br />
Here's the thingiverse mount file:<br />
[Thingiverse file](https://www.thingiverse.com/thing:4549542 "Thingiverse")<br />
BLTcouch offset with this mount:
```c
#define NOZZLE_TO_PROBE_OFFSET { -38, 3, -2.66 }
```

## FANS

The SKR 2 has 3 fans slots, I use the FAN2 to cool down the TMC2209, I used a conversion part to replace the Trigorilla to a SRK 2<br />
[Thingiverse file](https://www.thingiverse.com/thing:5139218 "Thingiverse")<br />
FAN 1 is used as part cooling<br />
FAN 2 is used to cool the hotend

## PINS TUNING

In case you have problems with this firmware version make sure that you are using the right pins:
[PINS MAP](https://github.com/bigtreetech/SKR-2/blob/master/Hardware/BIGTREETECH%20SKR%202-Pin.pdf "PINS MAP")

**Work in progess, wait for a stable version.**
