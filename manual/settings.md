---
title: "Settings"
description: "There are many settings and parameters that could be used to setup your printer on NanoDLP. Here we go through overview of those settings."
lead: "There are many settings and parameters that could be used to setup your printer on NanoDLP. Here we go through overview of those settings."
draft: false
menu:
  docs:
    parent: "manual"
images: []
toc: true
---
## Overview

There are two pages which you could access majority of the NanoDLP configurations.

### Machine settings

Containing general parameters indicate how your printer should works.

### Profile settings

You can define multiple print profile which could be used to adjust printer settings based on resin and other materials currently you are using. Some parameters on profile level could override machine level settings.

## Signs

There are some signs on NanoDLP to guide you through NanoDLP.

### Help ℹ

Link to on-screen or document containing help on those settings.

### Caution 🔥

These settings seems innocent but there are many kind of issues could be caused by wrong parameters here. It is better to not relay on them.

### Formula ∑

On-screen formula calculators help you see how changes on these inputs impact your prints.

### Regenerate ⟲

Change to the majority of NanoDLP options will be applied on-fly, that means you can change parameter during printing and see the result of those changes. But some parameters require re-slicing of the plate and would not applied during printing and will require plate regeneration.

## Printer Type

NanoDLP supports different printer types and each one does have different properties and behavior. 

### Projector / LCD

This is the default printer type and the only one that currently supports direct control. All settings function as intended for shield control.

When a ([code for curing]({{<ref "code">}})) is provided instead of relying on NanoDLP's default, the shield itself takes over cure time management. In this scenario, each layer is displayed entirely before the shield activates the UV LED to cure it. This approach is ideal for fast, high-resolution printers (8k+).

```
[[MoveCounterSet 0]]
G1 Z1; Move to layer
M104; UV LED On
G4 P1400; Cure layer
M105; UV LED Off
[[MoveWait 2]]; Both G1 and G2 returns Z_move_comp
```

### Laser
If you are using galvo laser type printer for SLA or SLS, this is the printer type you need to choose. In addition to usual "Projector LCD" type printers, instead of curing layer it generate gcode for shield in order to move laser source in x/y plane.

## More

* [Speed]({{<ref "speed">}})
* [Display Calibration]({{<ref "display-calibration">}})
