---
title: Picotool
---
Using the picotool utility to manipulate the Pico.
# How to use Picotool
Picotool is a command-line utility that can do useful things with a Pico connected over USB.
## Installation
The easiest way to install Picotool is to download and build it yourself: https://github.com/raspberrypi/picotool

A pre-built Windows executable is provided in the workshop repository inside the `tools` folder.
## Usage
Connect the Pico over USB and place it in `BOOTSEL` mode.

Get info on the connected Pico:
```shell
<path to picotool executable>/picotool.exe info
```

Upload an executable file to the Pico:
```shell
<path to picotool executable>/picotool.exe load build/onboard_led.uf2
```
- You can use the `load` command on a Pico that's not in `BOOTSEL` mode, as long as it has USB serial functionality enabled (Try with the [[serial-monitor|Serial Monitor]] programs).

Remotely reset the Pico:
```shell
<path to picotool executable>/picotool.exe reboot
```
