# skr_v2
Marling firmware using an Anycubic Chiron upgraded with an SKR 2 motherboard

HUGE THANKS TO EvilGremlin WHICH DID MOST OF THE WORK <3
SRK MCU

This firmware build is for the newer SKR 2.0 board, they mount the STM32F429 MCU, if you use the STM32F407 you will have to edit the line:
default_envs = BIGTREE_SKR_2_F429 
in platformio.ini (you will have to check to right code to use)

FIRMWARE

We are currently working on the bugfix Marlin version since in the latest release the STM32F407 MCU has not been implemented yet.

SENSORLESS HOMING

You will need the TMC2209 stepper drivers, and a BLTOUCH, you will need to make additional changes in case if:
- You have a different hotend mount (you will need to change the probe offset)
- You don't have the TMC2209, you will have to turn off the sensorless homing feature
- You don't have a BLTOUCH, you might still be able to use sensorless homing for the Y and X axis, but you will need to leave the stock z axis end stops.

Z double stepper motors

The chiron has 2 Z motors, to move each motor indipendently it's important to use the E1 slot in the motherboard to connect one of the Z stepper motor.
If you use the Z1 slot you will have both motors moving not indipendently.

TFT

The stock LCD was giving too much problems, the SKR 2.0 doesn't have a beeper pin in the TFT slot meaning the LCD would need a review and additional work which is not worth.
This firmware version works with a BTT TFT35 E3 V3.0 LCD.

Work in progess, wait for a stable version.
