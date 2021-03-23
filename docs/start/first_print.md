---
title: "The First Print"
description: "All steps after installation needed to start your first print with NanoDLP."
lead: "All steps after installation needed to start your first print with NanoDLP."
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu: 
  docs:
    parent: "start"
weight: 140
toc: true
---

{{< alert icon="💡" text="This section will go through basics to use NanoDLP and expect you already using hardware wired and ready to be used such as NanoDLP controller board." >}}

## Connect to NanoDLP

The main way to use NanoDLP is a web based interface that could be accessed through your local network. 

NanoDLP HDMI port being used to display and cure print layers, so it could not be used.

To find out Raspberry Pi or SBC IP you can use one of the ways below. After finding IP just need to open it through your browser.

### Using NanoDLP finder tool

Download, extract and run [NanoDLP Finder Tool](https://www.nanodlp.com/download/nanodlp-finder.zip).

### HMI interface

If you are using, HMI interface you can get IP details by touching WIFI icon on top right of the screen.

### Online dashboard

Visit [online dashboard](https://www.nanodlp.com/dashboard) to see online NanoDLP printers in your network.

### Router and OS network area panel

You can get your device IP by visiting administration panel of your router. Also your OS will detect NanoDLP on your local network, it will be accessible on Windows local area network.

### Making IP static

{{< alert icon="💡" text="Using this method is intended for intermediate to advanced users." >}}

You should plug SD card into a card reader and edit nanodlp-network.txt file to set a static IP on your device.

## Setup machine and resin settings

Go through following steps to make sure you will have functional printer.

1. Go to `machine settings` and make sure your printer `resolutions` is correct.
2. Go to `display calibration` and choose `boundary`, then control if it covered your whole display area.
3. Go to `axis calibration` and test zero point your build platform should be completely aligned with VAT surface.
4. Go to `axis calibration` and move up 1cm, measure if the movement is correct.
5. Go to `resin profile` and edit default/the first profile, check if cure times are correct.

## Upload and start your first print

1. Go to `plates` page.
2. Press add plate.
3. Choose STL file to print.
4. After slicing get completed click on the print button.
