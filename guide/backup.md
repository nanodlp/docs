---
title: "How to Backup and Restore"
description: ""
lead: ""
draft: false
images: []
menu: 
  docs:
    parent: "guide"
toc: true
---

SD card on Raspberry Pi could get corrupted as majority of users do not use [graceful shutdown]({{< ref "graceful-shutdown" >}}). Also power interrupts could cause same issue. So it is good to have backup around.

## Full backup

One of the options is to take full image from SD card, but it is both time consuming and inefficient. But there wide range backup solutions could take SD card image and restore.

## Which files and directories are important to take backup?

There are three types of files you may need to take backup.

* NanoDLP settings
* NanoDLP plates
* OS configurations

### NanoDLP settings and plates

There are two ways to do it automatic and manual.

#### Automatic backup / restore

Backup / Restore functions available on the tools page.

#### Manual backup / restore

There are two folders which you need to take a backup.

```
/home/pi/printer/db
/home/pi/printer/public/plates
```

To restore just terminate NanoDLP.

```
sudo service nanodlp stop
```

Then replace both folders and start nanodlp

```
sudo service nanodlp start
```

### OS configurations

Only way to do it without doing it manually is to use debug export from tools menu. Restoring is fully manual.
A debug file contains both OS and NanoDLP settings (without sensitive information such as wifi password and etc)

Important files such as config.txt may contains many important settings such as display configurations and hardware parameters. 
