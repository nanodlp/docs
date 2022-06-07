---
title: "Speed"
description: "Speed settings"
lead: ""
draft: false
images: []
toc: true
---

Speed settings only being used on direct control mode but for RAMPS and shield users, it is also accessible on code boxes.

## Types

### Setup

#### Min Speed
Being used when prints dip into resin.

#### Startup Speed
Being used for acceleration. It should not be to high, as it possible to lose steps.

#### Max Speed
Being used as the top speed when printer is not printing.

### Profile

#### Slow Section Speed
Speed which being used when distance of platform to tank floor is less than this value.

#### Max Speed
Max speed during printing

## Dynamic Speed
Override every speed excluding startup speed during printing. Will be used only for direct control.

Formula result will be used as length of each pulse in nano seconds.
In the best case scenario formula will run before each pulse, but to prevent delays it run less frequently in fast speeds.

Startup speed will be used until formula result become available.
