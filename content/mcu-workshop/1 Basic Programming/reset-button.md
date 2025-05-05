---
title: Reset Button
---
Using an external button to reset the Pico. This idea is so advanced, that Raspberry Pi did not think to include a button on the board.
# Components
- 1x 2-pin momentary tactile pushbutton
---
# Procedure
With the Pico inserted into a solderless breadboard, connect the button between pins `30 (RUN)` and `28 (GND)`. (Use the pinout diagram in [[pico-info|Raspberry Pi Pico 2 W]])

![[reset-button.png]]
Breadboard layout to add a reset button.

## Explanation
Whenever the `RUN` pin is connected to `GND`, the Pico will turn off. The pin has an internal pullup resistor to `VCC`, so once you break the connection and allow the pin voltage to return to $3.3\text{ V}$, the Pico will boot up and start running code from the beginning of the program. 

Pressing the button is equivalent to disconnecting and reconnecting the USB cable, but much more convenient!

## BOOTSEL mode
Now you can enter BOOTSEL mode by following the below sequence:
1. Press and hold both the BOOTSEL button and the reset button.
2. Release the reset button
3. Release the BOOTSEL button.