---
layout: default
title: Open boundary conditions
parent: Compound Flooding Models
permalink: docs/compound-flood/bctides
---

# Overview
Under the 2D setup, the bctides.in specifies 8 tidal constituents at a single open boundary with a format similar to ADCIRC's fort.15:
![Sample bctides.in](bctides.png)

# Scripts
A Python script is provide under the [pylib](https://github.com/wzhengui/pylibs) library prepared by Dr. Zhengui Wang:
```bash
pylibs//Scripts/gen_bctides.py

```
The usage is self-evident; you only need to read the "input" section at the beginning of the script.

Alternatively, if you have an existing bctide.in and only need to change the simulation period (temporally varying part),
you can use this script in SCHISM GIT:
```bash
[schism_git_dir]/schism/src/Utility/Tides/tide_fac_improved/tide_fac_improved
```
To generate hgrid.cpp from an existing hgrid.ll, you can do the following on the command line:
```bash

For a complete reference on "bctides.in", see the SCHISM manual and the sample under your SCHISM GIT directory:
```bash
[schism_git_dir]/schism/sample_inputs/bctides.in
```
