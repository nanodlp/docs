---
title: "NanoDLP / ZIP File Format"
description: "You can use this guide to understand NanoDLP file format."
lead: "You can use this guide to understand NanoDLP file format."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---
## Why a new file format?

NanoDLP parameters highly dynamic and being decided in realtime. It cause static parameters to not work well with NanoDLP. 

## NanoDLP file format

NanoDLP file format is a zip container file contains many files.

### .nanodlp vs .zip

NanoDLP processes zip file same as nanodlp but with extra check. So it will be same but slower to process.

## Files

ZIP file contains following files

* meta.json
* plate.json (Only require for NanoDLP format)
* Info.json
* override.json
* 3d.png
* 3d.png.meta
* profile.json
* PNG files 0~10000.png (Required)
* Plate raw file

### meta.json

It describes the program used to slice and prepare the file. It also indicate what could be used and enabled
```json
{
    "FormatVersion": 1,  # Current version of the export file
    "Distro": "generic", # Manufacturer or target printer 
    "Program": "NanoDLP",# Program used to prepare file
    "Version": "2038",   # Program version
    "OS": "linux",       # OS used to export it 
    "Arch": "amd64",	# Architecture used
    "Profile": false     # Is profile file should be used
}
```

### plate.json
General information about the exported plate/job

### info.json
Each layer details which could be used to calculate resin usage and shared to gcode and etc
```json
    {
        "TotalSolidArea": 468.47092,
        "LargestArea": 468.47092,
        "SmallestArea": 468.47092,
        "MinX": 560,
        "MinY": 941,
        "MaxX": 879,
        "MaxY": 1618,
        "AreaCount": 1
    },
```

### profile.json
Profile that used.

### override.json
Override resin profile settings for this specific plate.

### 3d.png and 3d.png.meta
200x100px 3D render of the current plate in PNG format. 
Layer PNG files
Each layer must be named starting from 0.png up to 100000.png layers without leading zero or any other name.

Format of the each PNG must be 8bit sRGB.

For mono displays each byte can represented a single pixel.

### Plate source file
Raw plate file which could be used on NanoDLP to re-slice. 
