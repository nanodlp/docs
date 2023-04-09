---
title: "Dimming"
description: "Pixel Dimming ensure the highest print quality along with an easy setup experience."
lead: ""
draft: false
images: []
toc: true
---
Pixel Dimming ensure the highest print quality along with an easy setup experience. This feature would have following effects by dimming the pixels:

* Prevents over-cure
* Preserves details
* Makes it possible to use one profile/cure time for different pieces with different thicknesses
* Increases the PDMS life time

<img src="https://www.nano3dtech.com/help/pixel-dimming.png" style="width:100%" alt="3D SLA Pixel Dimming">

## What is/are the reason(s) to use it?

Pixel Dimming somehow is a necessity on large, solid parts. The larger the area being cured for any
particular layer, the more of a runaway cure you will experience. That is why, the layer over cures
despite all attempts to prevent it through adjusting cure times. But by enabling Pixel Dimming, you can
fix it quite easily.

## How to use it?

It is available on resin profile

## Recommended settings

### FEP

* Dimming Type
  Checkerboard
* Dimming Amount
  20%
* Wall Around Dimmed Area in Pixels
  3 - Depends on x/y resolution
* Skip Layers
  40 - To have stronger support structure, you can turn off dimming for some number of layers

### PDMS

* Dimming Type
  Checkerboard
* Dimming Amount
  35%
* Wall Around Dimmed Area in Pixels
  3 - Depends on x/y resolution
* Skip Layers
  5
