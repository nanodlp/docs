---
title: "Troubleshoot"
description: ""
lead: ""
draft: false
images: []
menu: 
  docs:
    parent: "guide"
toc: true
---

* [Display Issues]({{< ref "raspberry-pi-display" >}})
* [USB Mounting]({{< ref "usb-mount" >}})

## Other issues

### Printer randomly stops

Usually it indicate communication issue between your Raspberry Pi / SBC and RAMPS board. NanoDLP waits for specific messages from RAMPS to do the synchronizations which may stalls if communicated data get corrupted between.

To verify it, you can visit activity log on NanoDLP or RAMPS terminal, you may notice some garbage characters in response from RAMPS.

To correct it:

* Make sure there is no insufficient or power fluctuation
* Make sure cable between RAMPS and Pi is fine

Another reason that may cause such issue is wrong configuration. When shutter code being used as it being processed in parallel with other code boxes. It could make NanoDLP receives commands in wrong order.
It is much better to move any gcode inside shutter inputs to before and after layer gcode boxes.

### Lines and artifacts on printed objects

May caused by bad synchronization. Synchronization keyword get passed earlier because of wrong command usage or bad wiring on shield <=> driver board.

Also having shutter gcode without wrong synchronization method may cause similar issues.
