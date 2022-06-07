---
title: "Improve Print Quality"
description: "NanoDLP contains advanced features to increase print quality."
lead: "NanoDLP contains advanced features to increase print quality."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---
* [Adaptive Layer Thickness]({{<ref "adaptive-thickness">}})
* [3D Anti-aliasing]({{<ref "aa-3d">}})
* Anti-aliasing
* [Dimming]({{<ref "dimming">}})
* [Barrel]({{<ref "barrel">}})
* [Mask Generator]({{<ref "mask-generator">}})

## Anti-aliasing

Anti-aliasing available on many modern slicer, NanoDLP apply AA as default on any 3D object. NanoDLP AA is not adjustable (only could be disabled) and apply limited amount of AA in order to not cause issue with majority of resin types.

### Anti-aliasing Threshold

Some resins does not cure well below specific light intensity. Anti-aliasing generate different shades of grey which lower intensity may cause bleeding effect on prints surface. You can define minimum % of light intensity required for curing specific resin.
