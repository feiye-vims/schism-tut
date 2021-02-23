---
layout: default
title: Horizontal grid in CPP
parent: Compound Flooding Models
permalink: docs/compound-flood/hgrid_cpp/
---

# Overview
In addition to hgrid.ll (lon/lat), some pre-processing scripts need the horizontal grid on a projected coordinate system.
The hgrid.cpp described here is based on CPP projection (see a description of the coordinate system <a href="https://www.xmswiki.com/wiki/CPP_Coordinate_System">here</a>).

# Scripts
A Fortran script is provide in Git to perform the projection from lon/lat to CPP:
```bash
[schism_git_dir]/src/Utility/Pre-Processing/NWM/Grid_manipulation/cpp.f90
```
, which requires the user input of the origin of the system in lon/lat.

This is also provided in:
```bash
[schism_git_dir]/src/Utility/Pre-Processing/NWM/Grid_manipulation/cpp.in
```
To generate hgrid.cpp from an existing hgrid.ll, you do the following on the command line:
```bash
cp -rL [schism_git_dir]/Grid_manipulation/ [your_run_dir]
cd [your_run_dir]/Grid_manipulation
./auto.pl
```
The perl automation runs the fortran script as "./cpp < cpp.in" and do some housekeeping.
Ignore the warning messages on hgrid.utm.\*, which is not used for the 2D setup.

The "Grid_manipulation" folder also contains small utilities that reproduce some frequently used functions of the Acetool.
