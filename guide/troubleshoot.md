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
  