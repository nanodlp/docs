---
title: "Raspberry Pi Display Issues"
description: ""
lead: ""
draft: false
images: []
toc: true
---
## Changing display settings

Editing display settings involve editing `/boot/config.txt` file but on recent version of NanoDLP it become much easier as you can do it by going to: 

**System menu > Tools page > Edit Raspberry Pi Settings**

For more information on available display settings on config.txt visit [Raspberry Pi config.txt video section](https://www.raspberrypi.org/documentation/configuration/config-txt/video.md).

## Display is rotated / flipped

Add one of lines below based on the issue, then reboot

```
# Normal
display_rotate=0
# 90 degrees
display_rotate=1
# 180 degrees
display_rotate=2
# 270 degrees
display_rotate=3
# horizontal flip
display_rotate=0x10000
# vertical flip
display_rotate=0x20000
```

## Missing or extra gap over border

Blank area over display border or part of image is missing.

You probably could fix it by playing with overscan settings.

```
disable_overscan=1
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0
```

## Only one third of display being used or one third is visible

Probably display is monochrome but you setup it on NanoDLP as RGB display or reverse.

## Display is blank or wrong picture

It means your display driver specifications are not detected correctly with Raspberry Pi [EDID](https://en.wikipedia.org/wiki/Extended_Display_Identification_Data). 

It is bit challenge to come up with correct values without display driver manufacturer help. Try correct HDMI related options on config.txt. Sometimes Pi4 and Pi3 configs could differ which makes things more difficult.

