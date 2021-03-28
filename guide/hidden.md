---
title: "Hidden Features"
description: ""
lead: ""
draft: false
images: []
menu: 
  docs:
    parent: "guide"
toc: true
---
{{< alert icon="💡" text="This guide intended for advanced users." >}}

There are many features available on NanoDLP interface but there are some features may rarely used which is not exposed in interface. 

Here you could find many of them and how to adjust each one.

## Machine and resin profile

Based on [folder structure guide]({{< ref "folder-structure#db" >}}) all configuration files are on the folder below:

```
/home/pi/printer/db
```

On this section we mostly focus on two files:

```
db/machine.json     # Machine settings (setup)
db/profiles.json    # Resin profile settings
```

To modify them stop NanoDLP, modify files then start it.

```
sudo service nanodlp stop
```

```
sudo service nanodlp start
```

### Machine settings

There are large number of settings (100+) here but majority of them already exposed, so only what not exposed listed and commented

```json
{
	"Name": "NanoDLP Generic",
	"Lang": "en",
	"Email": "",
	"Port": 80,
	"ReverseDirectionPin": 0,   /* Reverse axis for direct control */
	"FanOnGcode": "",           /* Fan gcode on  */
	"FanOffGcode": "",          /* Fan gcode off */
	"ShieldPause": "",          /* Shield pause gcode */
	"ShieldUnpause": "",        /* Shield un-pause gcode */
	"ShieldForceStop": "",      /* Shield force stop gcode */
	"TopGcode": "",             /* Top button gcode on axis calibration */ 
	"BottomGcode": "",          /* Bottom button gcode on axis calibration */
	"CalibrationGcode": "",     /* Calibration button gcode */
	"PressureType": 0,          /* Pressure sensor serial communication type */
	"PressureAddress": "",      /* Pressure sensor serial port address */
	"PressureSpeed": 0,         /* Pressure sensor serial port baud rate */
	"PressureRegex": "",        /* Pressure sensor regex to read information */
	"PressureDebug": false,     /* Pressure sensor data display on console */
	"ScaleClockPin": 0,         /* HX711 clock pin */
	"ScaleDataPin": 0,          /* HX711 data pin */
	"OpenScaleAddress": "",     /* OpenScale address */
	"PreviewWidth": 0,          /* 3D preview width in pixel */
	"PreviewHeight": 0,         /* 3D preview height in pixel */
}
```

### Resin profile settings

Settings here are going to be deprecated.

```json
[
	{
		"ProfileID": 1,
		"Title": "Generic Resin + Adaptive Layer Thickness",
		"Desc": "This profile using dynamic cure time to support adaptive layer thickness, pre-configured for NanoDLP controller board.",
		"LowQualityCureTime": 0,        /* Low quality layer cure time */
		"LowQualitySkipPerLayer": 0,    /* How many layers to skip */
		"XYResPerc": 0,                 /* Change on X and Y resolution as percentage */
	}
]
```


One of the options is to take full image from SD card, but it is both time consuming and inefficient. But there wide range backup solutions could take SD card image and restore.

## Hidden routes

There are 260+ routes on NanoDLP for different functionalities many of them are used but some not exposed and kept for advanced use. 

To use them call them through browser.

```
http://nanodlp_ip/hidden_url
```

Some of those hidden routes explained below: 

**/initGPU**  
Initialize GPU for OpenGL

**/slicer**  
Slicer's current status

**/debug/continue**  
Make printer continue if it stalled on Z_wait_complete [WaitForDoneMessage]

**/debug/verbose**  
More verbose logging

**/plate/temp/path**  
Last plate or temporary path

**/setup-simple**  
Simple setup page if available

**/printer/ip**  
Current printer IP addresses

**/printer/mem/free**  
Try free memory

### Post requests

These are more difficult to use

**/term-io**  
Send whatever gcode you need to the controller board

**/formula**  
Check [code / formula]({{< ref "code" >}}) processed results

**/slicer**  
Directly slice a STL/OBJ/SLC on NanoDLP through a call and receive result as ZIP file
