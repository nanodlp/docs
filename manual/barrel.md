---
title: "Barrel Correction"
description: "You can correct the barrel factor which is caused by projector lens."
lead: "You can correct the barrel factor which is caused by projector lens."
draft: false
images: []
menu:
  docs:
    parent: "manual"
weight: 1300
toc: true
---

## Why using barrel correction?

Projector lens cause [distortions](https://en.wikipedia.org/wiki/Distortion_(optics)) which may cause large object to deform. The main distortion caused by lenses called barrel distortion.

<img src="https://www.nanodlp.com/help/distortion-1.png" style="width:100%">

Using this feature you can eliminate effect during slicing by deforming sliced layers in reverse.

<img src="https://www.nanodlp.com/help/distortion-2.png" style="width:100%">

## How to use it?

You can define barrel correction value on slicer section of resin profile. The first you should define center of distortion and also factor.

Easiest way to test the output is to use ruler to see if lines on display calibration is straight or not.
