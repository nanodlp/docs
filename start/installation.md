---
title: "Installation"
description: "How to install NanoDLP on different platforms."
lead: "How to install NanoDLP on Raspberry Pi and other platforms."
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "start"
weight: 110
toc: true
---

## Raspberry Pi

One of the first decision you should make is if you want to use NanoDLP to generate pulses or you would use separate hardware such as RAMPS. As RAMPS provide many major advantages on this guide we focus on using NanoDLP with RAMPS.

### Requirements

To run NanoDLP you will need a separate hardware controller board, the main responsibility of this board is to drive stepper motor and other hardwares.

We recommend using NanoDLP official controller board but you can use any RAMPS compatible controller board. Our preferred firmware for RAMPS is Marlin which provide NanoDLP specific features internally.

### Raspberry Pi installation

There are two ways to install NanoDLP on Raspberry Pi. Easy and advanced one, the advanced one will require basic knowledge on how to connect to Raspberry Pi using SSH.

### Easy installation

1. Download [NanoDLP SD image](https://www.nano3dtech.com/nanodlp.img.gz)
2. Restore SD card image. 
2.1. [Windows](https://www.raspberrypi.org/documentation/installation/installing-images/windows.md)
2.2. [Mac](https://www.raspberrypi.org/documentation/installation/installing-images/mac.md)
2.3. [Linux](https://www.raspberrypi.org/documentation/installation/installing-images/linux.md)
3. Put SD card into Raspberry Pi and turn it on

### Advanced installation

1. Install [Raspberry Pi OS Lite](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit) on SD card.
2. SSH into Raspberry Pi and run the command below

{{< btn-copy text="(wget https://www.nano3dtech.com/download/nanodlp.linux.arm.rpi.stable.tar.gz --no-check-certificate -O - | tar -C /home/pi -xz --warning=no-timestamp);cd /home/pi/printer;sudo ./setup.sh" >}}

```bash
(wget https://www.nano3dtech.com/download/nanodlp.linux.arm.rpi.stable.tar.gz --no-check-certificate -O - | tar -C /home/pi -xz --warning=no-timestamp);cd /home/pi/printer;sudo ./setup.sh
```

## Other platforms (Windows, OSx, Linux Desktop)

1. Download appropriate file from the [download page](https://www.nano3dtech.com/nanodlp-download/).
2. Extract ZIP file.
3. The program is fully portable. You only need to run binary file. Make sure you are running binary from the same folder.
4. If you have issue running from file manager, from terminal go to the program's folder and run it from there.
5. Start using NanoDLP by opening [127.0.0.1](http://127.0.0.1:8080) link on your favorite browser.

## SBCs (Orange Pi, Rock Pi and etc)

1. Install basic Linux OS (no desktop environment) on SD card.
2. SSH into SBC and run the command below

### 64bit OS

{{<  btn-copy text="mkdir -p /home/nanodlp/;(wget https://www.nano3dtech.com/download/nanodlp.linux.arm64.beta.tar.gz --no-check-certificate -O - | tar -C /home/nanodlp -xz --warning=no-timestamp);cd /home/nanodlp/setup/server;sudo ./setup.sh" >}}

```bash
mkdir -p /home/nanodlp/;(wget https://www.nano3dtech.com/download/nanodlp.linux.arm64.beta.tar.gz --no-check-certificate -O - | tar -C /home/nanodlp -xz --warning=no-timestamp);cd /home/nanodlp/setup/server;sudo ./setup.sh
```

### 32bit OS

{{< btn-copy text="mkdir -p /home/nanodlp/;(wget https://www.nano3dtech.com/download/nanodlp.linux.arm.beta.tar.gz --no-check-certificate -O - | tar -C /home/nanodlp -xz --warning=no-timestamp);cd /home/nanodlp/setup/server;sudo ./setup.sh" >}}

```bash
mkdir -p /home/nanodlp/;(wget https://www.nano3dtech.com/download/nanodlp.linux.arm.beta.tar.gz --no-check-certificate -O - | tar -C /home/nanodlp -xz --warning=no-timestamp);cd /home/nanodlp/setup/server;sudo ./setup.sh
```

You can checkout more advanced guide on [installing NanoDLP on any Linux SBCs]({{< ref "sbc-installation" >}}).

## The next step

The next step you need to go through is [The First Print →]({{< ref "first_print" >}}).
