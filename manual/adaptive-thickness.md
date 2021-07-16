---
title: "Adaptive Layer Thickness"
description: "Adaptive layer thickness enable slicer to analysis whole object and slice it with different thicknesses depend on details on each level."
lead: "Adaptive layer thickness enable slicer to analysis whole object and slice it with different thicknesses depend on details on each level."
draft: false
images: []
toc: true
---
## Why using it?

Using *adaptive layer thickness* use can increase print quality without sacrificing print time.

## How to use it?

To use adaptive layer thickness you need to enter minimum and maximum layer thickness based on your resin and machine properties on resin profile.

As layers with different thickness will require different cure times you also need to enable and use *Dynamic Cure-time* input on the resin profile page to define cure time based on layer thickness

## Multiple Thickness

You can define different layer thicknesses on different parts of a print instead of relaying on automated algorithm. To use this feature use advanced section of the plate add page. 
```zone_height:thickness,zone_height:thickness,...```

For example ```5:100,100:25,150:100``` means

* For the first 5mm of the object, layer thickness is 100micron
* From 5mm to 100mm of the object, layer thickness is 25micron
* The remaining of the object up to 150mm should be printed 100micron


