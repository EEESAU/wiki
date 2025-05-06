---
title: Getting Started
---
This is the development environment setup guide for Raspberry Pi Pico 2 W
# VSCode (recommended for beginners)
## Installation
Install Visual Studio Code from the website: https://code.visualstudio.com/download
- On Linux, VSCodium needs special launch parameters to work with the Pico extension. The Microsoft version of VSCode works out of the box.

Open VSCode and install the [Raspberry Pi Pico Extension](https://marketplace.visualstudio.com/items/?itemName=raspberry-pi.raspberry-pi-pico).
![[pico-vscode-extension.png]]
## Making a new project
Click the Pico icon on the sidebar and select `New Project From Example`.
![[pico-new-project.png]]
Select the following project settings:
- Name: `picow_blink`
- Board type: `Pico 2 W`
- Select a project location

Once you press "Create", VSCode will begin downloading the toolchain for Raspberry Pi Pico.
- This step can take a few minutes as the toolchain is downloaded and installed.
## Uploading code to the Pico
Once the toolchain is finished downloading, VSCode will open the new project. Have a look at the `.c` files to read the code.

To compile the code, choose `Compile Project` from the sidebar menu.
![[vscode-pico-compile.png]]

The compiled files are inside the `build` folder.

> [!warning] BOOTSEL Mode
> BOOTSEL (Boot Select) is a special mode that you put the Pico in whenever you want to upload new code. 
> 
> To put the Pico into BOOTSEL mode:
> 1. Unplug the USB cable.
> 2. Hold down the BOOTSEL button.
> 3. Plug the USB cable back in.
> 4. Release the BOOTSEL button.
> 
> You should see the Pico appear as a USB storage device on your computer.
> 
> To upload new code, drag a `.uf2` file onto the Pico storage.

Put the Pico into BOOTSEL mode, then drag and drop the file `build/picow_blink.uf2` onto it.

The Pico should restart and the onboard LED should start blinking.
## Opening the Workshop Repository
[Look at the code repository for this workshop.](https://github.com/EEESAU/pico-workshop)

Download the code
```shell
git clone https://github.com/EEESAU/pico-workshop.git
cd pico-workshop
```
# Manual Setup
TODO