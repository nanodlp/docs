---
title: "Erode and Dilate"
description: "Reducing (erode) or expanding (dilate) the volume of an object by scaling the coordinates."
lead: "Reducing (erode) or expanding (dilate) the volume of an object by scaling the coordinates."
draft: false
images: []
toc: true
---
<img src="https://www.nano3dtech.com/help/erode-2.png">

## Why using erode or dilate?

Sometimes when printing without a raft, you may notice about the elephant’s foot, which means the first layer is slightly larger than the rest due to higher cure time.

While printing objects for practical applications, it can pose a large problem due to physical properties of resin such as shrinkage after it becomes solid. By using Erode and Dilate, you can resolve the issue.

Keep in mind the positive value represents the Dilate Areas and Erode Areas is defined by negative value.

<img src="https://www.nano3dtech.com/wp-content/uploads/2020/09/erode-1.png" style="width:100%">

## How to use it?

You can define erode or dilate on slicer section of resin profile.

## Limitations

Consider high erode or dilate value in combination with complex objects may cause unexpected result.
