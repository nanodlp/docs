---
title: "NanoDLP Controller Board"
description: "NanoDLP controller board advanced features"
lead: ""
draft: false
images: []
menu: 
  docs:
    parent: "guide"
toc: true
---

This guide will go through more advanced features of the NanoDLP controller board. For the basic guide, checkout [NanoDLP controller board](https://www.nanodlp.com/nanodlp-controller-board/) page.

## Change micro-stepping

To change you need to modify both jumpers on the controller board and also NanoDLP settings.

### Micro-stepping jumpers

You can find micro-stepping jumpers on top left of the board.

<img src="https://www.nanodlp.com/wp-content/uploads/2020/10/Stepper-Motor-Driver-1.png" width="80%" alt="NanoDLP Micro-stepping">

Based on table below you need to adjust jumpers.

| M0     | M1     | Step |
|--------|--------|------|
| GND    | GND    | 8    |
| VCC_IO | GND    | 32   |
| GND    | VCC_IO | 64   |
| VCC_IO | VCC_IO | 16   |

### NanoDLP settings

On the NanoDLP machine settings section (boot-up and start gcode inputs), you can find ``M92 Z3200`` which indicate micro-stepping and your axis pitch on Marlin. You need to update value accordingly.

## End switch / End limit

Default NanoDLP controller board support NPN and not PNP, using PNP require firmware change to do so you need to change Marlin config file before compiling that.

To understand end switch type try ```M119``` command on NanoDLP terminal, if the sensor is open and z_min triggered your end switch is PNP.

## Z-Axis height

Early NanoDLP controller board firmware limit Z-Axis height to 200mm on more recent one limit is 500mm. Modifying this limit require firmware flash/change.

## Marlin firmware

You can use [Marlin source code ready to use with NanoDLP controller board](https://github.com/nanodlp/Marlin/tree/nanodlp) to customize firmware on your controller board.

## NanoDLP Shield 

These are unofficial controller boards based on early NanoDLP hardware design, use of these board are not suggested due to weaknesses. 