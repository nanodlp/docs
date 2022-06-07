---
title: "Mask"
description: "Mask help you ensure even light output from any display."
lead: ""
draft: false
images: []
toc: true
---

Some of the light sources which have been used in SLA printers have uneven light issue.

To solve this problem, mask the file that is being used. It is basically a PNG file that modifies the pixel light output of each layer.

## Mask generator

Mask generator help you create mask file to ensure even light output from any display.

The generated mask file could be used on setup page to be applied on all jobs being sliced or individually during job creation.

You need UV sensor or an equivalent to use this feature.

### How to use it?

1. Go to display calibration and press mask generator button
2. Empty the Tank of resin and clean the Tank bottom surfaces inside and out.
3. Specify the number of measurement points in both x and y axis, and also the size of the measurement squares.
4. Tabular cells are displayed on the user interface. You can change the cell values from 0=black to 255=white.
5. When measuring, hold the UV sensor in the middle of the measurement square that is projected on the inside of the Tank.
6. Use the UV sensor to determine a set point value which is usually the lowest value of all measurement squares (probably the corner values)
7. Decrease the cell value for each measurement square until the UV sensor reads the set point value (do not press enter unless you want to display the mask)
8. Press preview and double check the surface area to see if UV intensity is the same across the entire Tank bottom.
9. Save mask (It takes up to a minute to generate a complete mask).
10. Go to Setup..Projector Mask to see the saved mask on the user interface (press refresh if necessary)

## Color

Rendering STL,SVG,SLC filled areas could be projected in any color. Ideally absolute white is the correct value for the projection and as light intensity is the highest it will decrease the cure time. But sometimes due to light bleeding full white color may not be suitable.

For the blank area, red color could preserve details better than black.
