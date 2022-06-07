---
title: "Direct Control"
description: "NanoDLP Direct Control"
lead: ""
draft: false
images: []
toc: true
---

You can use NanoDLP without using any kind of additional micro-controller. NanoDLP will generate pulse, even though it is much simpler to setup and easier to use. Due to uneven pulse generation using this method, it is much better to use [Shield]({{<ref "shield">}}) instead.

Following parameters are not useful if you are going to use [Shield]({{<ref "shield">}}).

The Raspberry Pi GPIO should be wired to the equivalent PIN on stepper motor drivers such as A4988 and DRV8825 directly.

## GPIO
Raspberry Pi GPIO has voltage limitation. A voltages near 3.3V. is interpreted as a logic high and a voltage near zero volts is a logic zero.

For more details about GPIO wiring, visit <a href="https://pinout.xyz/">Raspberry Pi pinout page.

## Endstop

Endstop switch must be placed on top of z-axis. This switch will be used for automatic z-axis calibration and position recovery. Endstop switch output should be high and when touched it should be low.

Also resetting may happens depend on settings if the end-stop switch triggered.

## Direction pin

High means upward movement and low means downward movement.

## Enable pin

If your driver has enable pin (such as DRV8825), wiring to Raspberry Pi provides a way to prevent any unwanted movements during Raspberry Pi bootup process. After bootup this pin output will be set to logical High and Low based on "Enable Pin State" setting.

## Microstepping

Microstepping value for Stepper driver, if you do not use any microstepping, put 1 as value.

2 for half step 
4 for 1/4
16 for 1/16
32 for 1/32

## Pitch

Distance travelled on each turn of Leadscrew
