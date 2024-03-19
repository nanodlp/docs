---
title: "Adding a Job"
description: "Adding a new job."
lead: "Adding a new job."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---

## Stop Layers?

Makes printer to stop on specific layers. The list of layers should be comma separated.
eg. 100,200,300

## Centering

Effects the position of STL/SLC/SVG source file which is being rendered in the plate.

### Auto Center

Centers the pieces in the middle of the plate.

### Disable

Respects zero point from the 3D program which the file has been exported with. The 3D program's origin point will be at the bottom left of the plate.

### Center Origin

Draws 3D program's origin (center) point to the center of the plate.

