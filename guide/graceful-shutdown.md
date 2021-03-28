---
title: "Graceful Shutdown"
description: "Powering off Raspberry Pi without proper shutdown could cause SD card corruption and force users to re-flash SD cards time to time."
lead: "Powering off Raspberry Pi without proper shutdown could cause SD card corruption and force users to re-flash SD cards time to time."
draft: false
images: []
menu: 
  docs:
    parent: "guide"
toc: true
---

By using this feature NanoDLP listens to GPIO if state of GPIO changed to the required state, it will shutdown the printer during the idle mode and during the print it will stop the printer.

## How to use graceful shutdown?

To complete power-off it is possible to use Raspberry Pi kernel parameters (config.txt) to let external controller know that Pi is switched off. So it can cut the power completely.
GPIO state changes just after complete Raspberry Pi shutdown.

* Name  
      gpio-poweroff

* Info  
      Drives a GPIO high or low on poweroff (including halt). Enabling this overlay will prevent the ability to boot by driving GPIO3 low.
* Load  
      dtoverlay=gpio-poweroff,param=val

* Params  
  * gpiopin  
      GPIO for signalling (default 26)

  * active_low  
      Set if the power control device requires a
            high->low transition to trigger a power-down.
            Note that this will require the support of a
            custom dt-blob.bin to prevent a power-down
            during the boot process, and that a reboot
            will also cause the pin to go low.

  * input  
      Set if the gpio pin should be configured as
            an input.

  * export  
      Set to export the configured pin to sysfs

  * timeout_ms  
      Specify (in ms) how long the kernel waits for power-down before issuing a WARN (default 3000).
      
      eg. dtoverlay=gpio-poweroff,gpiopin=20
