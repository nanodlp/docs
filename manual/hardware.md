---
title: "Hardware"
description: "NanoDLP supports different hardware accessories."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---

NanoDLP supports different hardware accessories, you could find some of them below.
There is a different manual covering [Shield]({{<ref "shield">}}).

## Camera

Call external program to take photos. To use Raspberry Pi official camera you can use command below.

```
raspistill --output {{file}} --nopreview
```

## GPIO

Raspberry Pi GPIO has voltage limitation. A voltages near 3.3V. is interpreted as a logic high and a voltage near zero volts is a logic zero.
For more details about GPIO wiring, visit <a href="https://pinout.xyz/">Raspberry Pi pinout</a> page.

### Fault detection

Freeze operation if GPIO mode indicate fault. (eg. stepper driver fault pin)

### Wait pin

To synchronize movements (letting nanoDLP know when a movement is finished) this pin could be used. nanoDLP waits for the pin to be LOW. At the start of movement, controllers / drivers must make this pin HIGH and at the end of movement make it LOW. The maximum delay for detection is 1ms.

### Shutdown

Powering off Raspberry Pi without proper shutdown could cause SD card corruption and force users to reflash SD cards time to time. By enabling this function NanoDLP listens to GPIO if state of GPIO changed to the required state, it will shutdown the printer during the idle mode and during the print it will stop the printer.

#### Graceful Shutdown

To complete power-off it is possible to use Raspberry Pi kernel parameters (config.txt) to let external controller know that Pi is switched off. So it can cut the power completely.
GPIO state changes just after complete Raspberry Pi shutdown.

gpio-poweroff

Drives a GPIO high or low on poweroff (including halt). Enabling this overlay will prevent the ability to boot by driving GPIO3 low.

dtoverlay=gpio-poweroff,param=val

gpiopin: GPIO for signalling (default 26)
active_low: Set if the power control device requires a
            high->low transition to trigger a power-down.
            Note that this will require the support of a
            custom dt-blob.bin to prevent a power-down
            during the boot process, and that a reboot
            will also cause the pin to go low.

input: Set if the gpio pin should be configured as an input.
export: Set to export the configured pin to sysfs
timeout_ms: Specify (in ms) how long the kernel waits for
            power-down before issuing a WARN (default 3000).
Example: dtoverlay=gpio-poweroff,gpiopin=20


## Shutter

In addition to shutter support through GCode, it is also possible to wire the shutter directly to Raspberry Pi GPIO.

* Servo Motor: By wiring the pulse pin of the servo motor to GPIO you can control the shutters directly.
* True/False: Makes GPIO HIGH and LOW suitable for magnetic shutters or to separate the shutter control boards.

### Servo

Usually shutter servo motors require pulse width between 500μs-2500μs for min and max positions. But servo motor tolerates less stress if you use smaller ranges such as 700μs-2300μs.

Set pulse time length as long as the shutter needs to travel from open to close position.

Do not wire shutter power to Raspberry Pi itself as it could have negative effect on Raspberry Pi.

## Projector

* USB / Serial - ASCII (\r\n): Communicate in ASCII mode and end commands with carriage return + new line
* USB / Serial - ASCII (\r): Communicate in ASCII mode and end commands with carriage return
* USB / Serial - ASCII (\n): Communicate in ASCII mode and end commands with new line
* USB / Serial - Binary: Communicate in Binary mode

## DSI HMI

DSI interface could be used to drive touchscreen display as HMI. Currently different image required to use NanoDLP+DSI HMI together. In addition to separate process for DSI following changes applied to make DSI works together with NanoDLP.

* Changing default display id to two from NanoDLP setup page.
* Add following command to config.txt "dtoverlay=vc4-fkms-v3d"

## Nextion

Nextion displays being supported by NanoDLP internally.
To use them you need to load NanoDLP HMI on Nextion Display and enter correct address on NanoDLP.
If you are connecting Nextion to Raspberry Pi without Serial2USB adapter, you need to enable serial on 

Raspberry Pi by following steps below:

1. SSH into your Raspberry Pi
2. Run command: sudo raspi-config
3. Enable Serial
4. sudo nano /boot/cmdline.txt
5. remove command "console=ttyAMA0,115200" and "console=serial0,115200"
6. sudo nano /boot/config.txt
7. Add following line: dtoverlay=pi3-disable-bt
8. sudo reboot

For more information visit <a href="https://www.raspberrypi.org/documentation/configuration/uart.md">Raspberry Pi UART</a> page.

## Lamp

Serial command to query the hours of the projector's lamp.
Acer

```* 0 Lamp```

Infocus

```(LMP?)```

### Output

The light output of the projectors degrade over time. At the end of rated lamp's life, brightness could decrease down to %50. The change is not linear specially in early stages but it is close enough.

You can specify what percentage each 100 hours in a lamp life should increase the cure time, so you would not need to adjust the cure times manually.

For the standard lamps we recommend 2.5.

