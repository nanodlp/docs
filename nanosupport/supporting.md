---
title: "Supporting"
description: "Supporting description"
lead: ""
draft: false
images: []
menu: 
  docs:
    parent: "nanosupport"
toc: true
---

Supporting tool is used to place support parts under surfaces that have potential to collapse while printing.

## Select Support Size

There are three predefined support size templates. Small, Medium and Large.

## Edit Support Templates

Each support template can be edited and saved permanently by click on the small triangle at corner of it or right click or press and hold or double click on each template.

## Support Modes

By selecting "Auto Support" checkbox, the application uses both auto generated and manually made placeholders. otherwise it just uses manual placeholders.

## Auto Support

By using "Auto Support", NanoSupport application calculates support points by given parameters and shows auto support placeholders represented by small spherical shapes on the object. then the "Generate" button starts making supports on desired placeholders.

> ### Floor Pad Checkbox
>
> Checking this option joins base parts of all supports in one piece, like all support stalks grow from within a pool.

> ### Parameters
>
> #### Density
>
> Density of supports. used when checking "Auto Support".
>
> #### Lowest Gap
>
> Description of lowest gap here.

## Manual Support

When the "Auto Support" is not checked, it's just manual. so by click on each object in scene a manual support placeholder will be set and shown as a cone pointed to desired point. and click on each cone will delete it. At the end, "Generate" button makes support structures on all placeholders.