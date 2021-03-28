---
title: "Remote Slicing"
description: "Remote slicing is the capability of handing over the process of slicing to a remote desktop computer
or server."
lead: "Remote slicing is the capability of handing over the process of slicing to a remote desktop computer
or server."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---

## What is/are the reason(s) to use remote slicing?

On boards like Raspberry Pi, the process of slicing large STL files could take up to 30 minutes, whether on a normal Personal Computer, it takes about 2 to 3 minutes. By using Remote Slicing your waiting time decreases significantly.

## How to use remote slicing?

There are three ways to use Remote Slicing:

### Automatic

If you have installed NanoDLP on your Personal Computer, try to connect to NanoDLP on Raspberry Pi by opening your favorite browser. Once you upload a plate on NanoDLP Raspberry Pi, the NanoDLP on your Personal Computer will be detected and the process of slicing is going to start remotely.

### Manual setup

Navigate through **System > Machine Settings > Slicing > Remote slicing** and enter the IP alongside the Port number.

IP could be private (local) network IP or public IP / port forwarding, loopback IP (127.0.0.1 / 0.0.0.0) should not used. Default port is usually 80 for Raspberry and 8080 for other devices. Checkout [this guide](https://www.tp-link.com/us/support/faq/838/#windows%2010) if you are not sure how to find your IP address.

<img src="https://www.nanodlp.com/help/remote-slicing.png" style="width:100%">

### NanoSupport

NanoSupport has embedded NanoDLP inside which detect your printers and resin profile slice locally then automatically update files to your chosen printers.

## How remote Slicer works

1. NanoDLP installed on Raspberry Pi and Windows computer being used by user.
2. A new plate uploaded to Raspberry Pi.
3. Raspberry Pi NanoDLP detects active NanoDLP installation on users' Windows computer.
4. Raspberry Pi transfer required data to Windows.
5. NanoDLP on Windows start processing.
6. NanoDLP on Raspberry Pi get status update from Windows version. And wait until slicing get completed.
7. NanoDLP on Raspberry Pi fetch prepared data.

## Troubleshoot

You need to add inbound connection exception on your firewall to make NanoDLP on your PC/Mac accessible, usually your OS will ask for permission upon running NanoDLP but if it does not, you need to do it manually.
