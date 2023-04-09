---
title: "Shield / RAMPS"
description: "Best way to use NanoDLP is to have separate controller board. Here you could find more details on available options and best practices."
lead: "Best way to use NanoDLP is to have separate controller board. Here you could find more details on available options and best practices."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---

## Why shield?

You can have fully functional 3D SLA printer without using extra controller with NanoDLP direct control but it strongly advised to use RAMPS or any similar board.

## Hardware choices

Any RAMPS compatible Atmel (Arduino) and ARM boards could be used as controller, you can use [NanoDLP controller board](https://www.nano3dtech.com/nanodlp-controller-board/) which is ready to use without modification. 

### Protocol

Different protocol such as serial (USB) and i2c supported to communicate with shield.

### Encoding

* ASCII Encoding: Adds line terminations (\r\n) automatically. Suitable for firmware such as Marlin.
* Binary Encoding: Removes any new line and converts base16 to binary. Suitable for Trinamic like of boards.

### Firmware

There are many firmwares but due to official NanoDLP support, our preferred firmware is [Marlin](https://marlinfw.org/). It fully support NanoDLP movement synchronization with [single config change](https://github.com/MarlinFirmware/Marlin/blob/2.0.x/Marlin/Configuration_adv.h#L3437). 

Other firmware also could be used but for synchronization purpose you need to use NanoDLP patched version, without patched version you may need to use other mechanisms for synchronization which is a more difficult to setup.

## How to setup shield?

Currently this guide does not cover wiring as it may differ based on your hardware choice. 

Find correct address of the RAMPS using details below then enter correct path on the **System > Machine Settings > RAMPS / Controller**.

### Raspberry Pi / Linux Version

USB/Serial ports usually listen to one of these addresses:

* /dev/ttyACM0
* /dev/ttyACA0
* /dev/ttyUSB0

To find out the correct address you can connect to Raspberry through SSH protocol using tools such as Putty. Run the following command and take notes of the available paths.

```ls /dev/tty*```

Connect your device to Raspberry Pi and type the above command again. The additional path belongs to your device.

### Windows Version

Enter the RAMPS COM port address.
Steps to find the correct COM port in windows:

1. Open the "Run" dialog box by pressing and holding the Windows key, then press the R key ("Run").
2. Type devmgmt.msc and press enter.
3. Check out Ports section of the device manager.
