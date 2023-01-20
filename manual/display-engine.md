---
title: "Display Engines"
description: "NanoDLP supports different type of communication with your display, here you could find brief description on each one."
lead: "NanoDLP supports different type of communication with your display, here you could find brief description on each one."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---

## BCM (DispmanX)

{{< alert icon="💡" text="It is going to be deprecated by Raspberry Pi foundation." >}}

It is a way to communicate directly with Raspberry Pi (Broadcom chipsets) to display images. Performance is great but only works on Raspberry Pi.

No option needed to enable it, it automatically being used on Raspberry Pi if other display engine does not enabled manually.

## Direct

Linux only solution, if there is available support on Linux kernel, it try to list and use available graphic interfaces on the kernel. The current implementation does use buffers to speedup displaying large images (8K+). Memory usage on this engine is quite higher than the others.

## Framebuffer

This is very basic form of updating display on Linux and Mac. Just need to put correct path to enable it instead of BCM.

## OpenGL

It is desktop only solution, due to possible timing and reliability issue on desktop computers using NanoDLP on desktop environment not suggested.

## BCM (DispmanX) vs. Framebuffer vs. OpenGL

| Support                      | BCM   | Framebuffer                    | OpenGL | Direct |
|------------------------------|-------|--------------------------------|--------|--------|
| Raspberry Pi w. Server OS    | Yes   | No                             | No     | Yes    |
| Raspberry Pi w. Full OS      | No    | Yes (1)                        | Yes    | Yes (1)|
| Linux – Server (ARM, AMD64)  | No    | Yes                            | No     | Yes    |
| Linux – Desktop (ARM, AMD64) | No    | Yes (1)                        | Yes    | Yes (1)|
| Windows                      | No    | No                             | Yes    | No     |
| Mac                          | No    | No (There are some workaround) | Yes    | No     |
| Performance (FPS)            | Good  | Average                        | Average| Great  |
| Compatibility                | Good  | Great                          | Good   | Good   |
| Stability                    | Great | Great                          | Good   | Great  |
| Memory Usage                 | Great | Good                           | Good   | Average|

1. Should be enabled on the most cases.


## Display Number

It is possible to use HDMI, DSI and GPIO to connect displays to Raspberry Pi. To use HDMI output value must be 0 and for the other type of displays value usually is 1. If both DSI and HDMI connected usually HDMI will start from 2.

On Windows and Linux desktop, having zero value will make NanoDLP choose secondary display automatically. For force NanoDLP use primary display use value 1 and for secondary use 2.
