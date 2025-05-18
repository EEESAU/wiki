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
## Opening the Workshop Repository
[Look at the code repository for this workshop.](https://github.com/EEESAU/pico-workshop)

Inside VSCode, go to the File Explorer. Press "Clone Repository" and paste the following URL: `https://github.com/EEESAU/pico-workshop.git`
![[vscode-clone-repo.png]]

Once the project is opened, VSCode will automatically begin downloading the toolchain for Raspberry Pi Pico.
- View the progress in the notifications at the bottom right.
- This step can take a few minutes as the toolchain is downloaded and installed.
## Uploading code to the Pico
Once the toolchain is finished downloading, VSCode will open the new project. 

Open the file `onboard_led.c` in the root directory.
- This is a short program that turns on an LED built onto the Raspberry Pi Pico 2 W.

To compile the code, choose `Compile Project` from the sidebar menu.
![[onboard_led_compile.png]]

Once the compilation is finished, the executable files will be inside the `build` folder. 

These files are specially built for the Raspberry Pi Pico 2 W, and they won't run on your computer. To see how they work, we need to load them onto the Pico so it can run them.

> [!warning] BOOTSEL Mode
> BOOTSEL (Boot Select) is a special mode that you put the Pico in whenever you want to upload new code. 
> 
> To put the Pico into BOOTSEL mode:
> 1. Unplug the USB cable. (If you already had it plugged in)
> 2. Hold down the BOOTSEL button.
> 3. Plug the USB cable back in.
> 4. Release the BOOTSEL button.
> 
> You should see the Pico appear as a **USB storage device** on your computer.
> 
> To upload new code, drag a `.uf2` file onto the Pico storage.

Put the Pico into BOOTSEL mode, then drag and drop the file `build/onboard_led.uf2` onto it.

Once the file finishes copying, the Pico will disconnect and the green light will turn on. It just ran our code!

At this point, you're ready to move on with the rest of the workshop. Go to [[mcu-workshop/1 Basic Programming/index|Basic Programming]] first.
# Manual Setup (If you don't want to use VSCode)
You will need to install the following dependencies:
- GNU ARM bare metal toolchain (`arm-none-eabi-gcc`)
- CMake

Download the workshop repository:
```shell
git clone https://github.com/EEESAU/pico-workshop.git

cd pico-workshop
```

Enable the setting to download Pico SDK automatically:
```shell
export PICO_SDK_FETCH_FROM_GIT=1
```

Run CMake to generate build files:
```shell
cmake -S . -B build
```