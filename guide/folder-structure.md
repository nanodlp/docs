---
title: "Folder Structure"
description: "Knowing NanoDLP folder structure could be useful for many cases such as data migration, recovery and advanced configuration."
lead: ""
draft: false
images: []
menu: 
  docs:
    parent: "guide"
weight: 1000
toc: true
---

Knowing NanoDLP folder structure could be useful for many cases such as

* Migrating your installation to a new SD card.
* Recover corrupted SD card.
* Modify configuration manually.

## Structure Overview

Below you could find the basic folder structure after installation on Raspberry Pi and brief description of the each one.

```
├── config
│   ├── nanodlp.service
│   ├── nanodlp-wifi.txt
│   ├── printer.rotate
│   └── run.sh
├── db
├── distro
├── build
├── expand-fs.sh
├── LICENSE
├── NOTICE
├── printer / nanodlp
├── public
│   ├── alert.ogg
│   ├── css
│   │   ├── main.css
│   │   └── support.css
│   ├── favicon.ico
├── setup.sh
└── templates
```

## Folders 

### db/

This is the most important folder as it contains many json files which keep all of your NanoDLP configurations.

### public/

All static files that being served for users including theme files being served from here.

### public/plates/

All plates that being added to NanoDLP to printer saved into this folder.

### templates/

Include both theme HTML files and HELP files.

### distro/

Default files for each distribution including manufacturer specific config and theme files.

### config/

It includes basic OS config files for Raspberry Pi that being used by setup.sh


## Main Files

### printer / nanodlp

This the main executable to run nanodlp. Also on linux desktop you may have file called run.sh that could be used to run nanodlp.

One of the way that you can check if the nanodlp installed correctly or not (on Pi) is to run command below:

sudo ./printer

### setup.sh

It is script that install NanoDLP on Raspberry Pi.

### expand-fs.sh

Script to expand file system on SD card.

## Other Files

{{< alert icon="💡" text="This section intended for intermediate to advanced users." >}}


### build

File that indicate current installation manufacturer or customization name.


### public/alert.ogg

Bird sound that being played after print completion.

### nanodlp.service

This is systemd service file that being installed during setup. You can install it on any linux computers.

Following command are the most used systemd command on linux for nanodlp.

* status
* stop
* start
* restart
* disable

Get current status 

```bash
pi@raspberrypi:~ $ sudo service nanodlp status
● nanodlp.service - NanoDLP service
   Loaded: loaded (/etc/systemd/system/nanodlp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2021-03-18 21:17:04 UTC; 5 days ago
 Main PID: 232 (bash)
    Tasks: 20 (limit: 1942)
   CGroup: /system.slice/nanodlp.service
           ├─232 /bin/bash /home/pi/printer/run.sh
           ├─363 sudo ./printer
           └─368 ./printer
```


### nanodlp-wifi.txt and nanodlp-network.txt

Manual configuration files for Ethernet and WiFi connection.
