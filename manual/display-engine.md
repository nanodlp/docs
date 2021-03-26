---
title: "Display Engines"
description: "NanoDLP supports different type of communication with your display, here you could find brief description on each one."
lead: "NanoDLP supports different type of communication with your display, here you could find brief description on each one."
draft: false
images: []
menu:
  docs:
    parent: "manual"
weight: 1300
toc: true
---

## BCM (DispmanX)

It is a way to communicate directly with Raspberry Pi (Broadcom chipsets) to display images. Performance is great but only works on Raspberry Pi.

No option needed to enable it, it automatically being used on Raspberry Pi if other display engine does not enabled manually.

Only reason not use it on Raspberry Pi is when NanoDLP DisplaymanX is not compatible with your display in forms of reliability issue.

## Framebuffer

This is very basic form of updating display on Linux and Mac. Just need to put correct path to enable it instead of BCM.

## OpenGL

It is desktop only solution, due to possible timing and reliability issue on desktop computers using NanoDLP on desktop environment not suggested.

## BCM (DispmanX) vs. Framebuffer vs. OpenGL

| Support                      | BCM   | Framebuffer                    | OpenGL |
|------------------------------|-------|--------------------------------|--------|
| Raspberry Pi w. Server OS    | Yes   | No                             | No     |
| Raspberry Pi w. Full OS      | No    | Yes (Should be Enabled)        | Yes    |
| Linux – Server (ARM, AMD64)  | No    | Yes                            | No     |
| Linux – Desktop (ARM, AMD64) | No    | Yes (Should be Enabled)        | Yes    |
| Windows                      | No    | No                             | Yes    |
| Mac                          | No    | No (There are some workaround) | Yes    |
| Performance (FPS)            | Great | Good                           | Good   |
| Compatibility                | Good  | Great                          | Good   |
| Stability                    | Great | Great                          | Good   |


