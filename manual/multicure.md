---
title: "Multi-cure"
description: "By using multi-cure, you can print a single object with the different cure times at the same time."
lead: "By using multi-cure, you can print a single object with the different cure times at the same time."
draft: false
images: []
menu:
  docs:
    parent: "manual"
toc: true
---

## What is/are the reason(s) to use multi-cure?

If you do not want to waste your time printing the same object over and over again to get perfect print, you should try multi-cure.

Using the new feature you can choose multiple cure times for the same object during plate upload and with single print you can get multiple copy of the same object with different cure times.

Whole print will takes as much as time required for the single plate using highest chosen cure time.

<img src="https://www.nano3dtech.com/help/multicure.png" style="width:100%">

## How to use it?

On the plate add page, there are a button called *advanced*, click and enter whatever cure times you need.

Base cure time for the current profile, also will be added to cure times.

Print the same object with multiple cure times all at once. The chosen profile's settings will be applied on all copies except normal layer cure times.

In addition to all specified cure times, an extra object will be printed using profile cure time. It only will replace normal layer cure time and would not affect burnin layers.

For example if there is 3 cure times specified: 3,4,5 and chosen profile cure time is 2.5. Four copies of the object will be printed with following cure times 2.5,3,4,5

If there is not enough space to print all cure times, lowest ones will be chosen.

On profile level it is possible to modify gap around objects.