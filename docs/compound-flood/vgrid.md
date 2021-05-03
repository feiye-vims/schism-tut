---
layout: default
title: Vertical grid in 2D
parent: Compound Flooding Models
permalink: docs/compound-flood/vgrid
---

SCHISM does not use an explicit option to distinguish between a 2D model and a 3D model.
Instead, it offers the flexibility to individually assign the number of layers at each horizontal node.
The simplest way to make a vertical grid for a 2D model is to use the sigma coordinate on all grid nodes.

You can directly use this [vgrid.in](http://ccrm.vims.edu/yinglong/feiye/Workshop_20190701/Delaware/2D/vgrid.in) for any 2D model.
It is a simple ASCII file, specifying a terrain-following grid with only a surface and a bottom (i.e., one vertical cell).
