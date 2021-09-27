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

Usually a display driver manufacturer help needed to come up with correct configuration. You should contact the display seller first, if it does not help on the [online Raspberry Pi display configuration sheet](https://docs.google.com/spreadsheets/d/1hSdkwEbtTrVbtTAgvv-0QcyMbztVJvU7GvOmZ8gp5Vk/edit#gid=0) you can find some configuration files for popular displays.

Consider below points during your journey to come up with correct configurations.

* Sometimes Pi 4 and Pi 3 configs could differ
* Some items may seems unrelated but could affect HDMI output
* Pi 4 supports two displays, you can assign separate config to each port separately. Specially useful to save memory to prevent memory allocation to empty port.

### Use EDID tools to extract HDMI timing

Sometimes manufacturers are not accessible or share wrong specs, one of the way is to extract this information automatically. To do so first you need to SSH into your Raspberry Pi. Install ```read-edid``` using command below:

```
sudo apt install read-edid
```

Then by running following command you can get supported display modes.

```
sudo get-edid | parse-edid
```

As an example below you could find a sample output of the command. 

```
This is read-edid version 3.0.2. Prepare for some fun.
Attempting to use i2c interface
No EDID on bus 0
No EDID on bus 2
No EDID on bus 3
No EDID on bus 4
1 potential busses found: 1
256-byte EDID successfully retrieved from i2c bus 1
Looks like i2c was successful. Have a good day.
Checksum Correct

Section "Monitor"
	Identifier "VX279"
	ModelName "VX279"
	VendorName "ACI"
	# Monitor Manufactured week 23 of 2015
	# EDID version 1.3
	# Digital Display
	DisplaySize 600 340
	Gamma 2.20
	Option "DPMS" "true"
	Horizsync 30-83
	VertRefresh 56-75
	# Maximum pixel clock is 150MHz
	#Not giving standard mode: 1152x864, 75Hz
	#Not giving standard mode: 1280x1024, 60Hz
	#Not giving standard mode: 1280x1024, 75Hz
	#Not giving standard mode: 1680x1050, 60Hz
	#Not giving standard mode: 1280x960, 60Hz
	#Not giving standard mode: 1440x900, 60Hz
	#Not giving standard mode: 1600x1200, 60Hz

	#Extension block found. Parsing...
	Modeline 	"Mode 11" 148.50 1920 2008 2052 2200 1080 1084 1089 1125 +hsync +vsync 
	Modeline 	"Mode 0" 148.50 1920 2008 2052 2200 1080 1084 1089 1125 +hsync +vsync 
	Modeline 	"Mode 1" 148.500 1920 2008 2052 2200 1080 1084 1089 1125 +hsync +vsync
	Modeline 	"Mode 2" 74.250 1280 1390 1420 1650 720 725 730 750 +hsync +vsync
	Modeline 	"Mode 3" 27.027 720 736 798 858 480 489 495 525 -hsync -vsync
	Modeline 	"Mode 4" 25.200 640 656 752 800 480 490 492 525 -hsync -vsync
	Modeline 	"Mode 5" 74.250 1920 2448 2492 2640 1080 1082 1089 1125 +hsync +vsync interlace
	Modeline 	"Mode 6" 27.000 720 732 796 864 576 581 586 625 -hsync -vsync
	Modeline 	"Mode 7" 74.250 1920 2008 2052 2200 1080 1082 1087 1125 +hsync +vsync interlace
	Modeline 	"Mode 8" 148.500 1920 2448 2492 2640 1080 1084 1089 1125 +hsync +vsync
	Modeline 	"Mode 9" 148.500 1920 2008 2052 2200 1080 1084 1089 1125 +hsync +vsync
	Modeline 	"Mode 10" 74.250 1280 1720 1760 1980 720 725 730 750 +hsync +vsync
	Modeline 	"Mode 12" 74.25 1920 2008 2052 2200 540 542 547 562 +hsync +vsync interlace
	Modeline 	"Mode 13" 74.25 1280 1390 1430 1650 720 725 730 750 +hsync +vsync 
	Modeline 	"Mode 14" 27.00 720 736 798 858 480 489 495 525 -hsync -vsync 
	Option "PreferredMode" "Mode 11"
EndSection
```

## Additional Resources

If your display does work strangely, the issue probably caused by wrong HDMI timing. Check out below post on how to [get correct timing on Raspberry Pi](https://www.raspberrypi.org/forums/viewtopic.php?t=224229&fbclid=IwAR1RERZ60jAkD_Za0kjIn3Rfu5C6Jb03SGnqTIXbhF47ZqB0MhGemo5AYag).
