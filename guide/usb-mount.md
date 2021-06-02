---
title: "USB Mount"
description: ""
lead: ""
draft: false
images: []
toc: true
---
## Auto Mount USB

Process below being setup automatically on your Raspberry Pi (or any other SBC) to auto mount USB flash disk. 
To do it manually you need to do following actions using SSH.

### Install required packages

``` 
sudo apt-get install usbmount ntfs-3g pmount 
```

### Change parameters

Edit file
```
sudo nano /lib/systemd/system/systemd-udevd.service 
```

Modify below parameters, if any of them missing no need to add them.

```
PrivateMounts=yes to PrivateMounts=no
MountFlags=slave to MountFlags=shared
```

## Troubleshooting

Sometimes various issues cause USB does not detected by Linux.
If USB detected correctly you should be able to see files on NanoDLP. If not to confirm if disk is mounted or not you can run command below to get list of mounted storages.

```
ls -l /media/*
```

If above command return empty list, it indicate usb storage is not mounted. By using command below you could confirm if the disk is detected by Linux.

```
sudo fdisk -l
```

If your storage listed, it means it detected but because of filesystem or another compatibility issue it could not be mounted.
Usually it is better to have your storage formatted in FAT format or other Linux compatible filesystem.
