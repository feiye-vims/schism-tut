---
layout: default
title: Bathymetry loading
parent: Compound Flooding Models
nav_order: 1
---

# DEM files
DEM files used in the ECGC (East Coast and Gulf Coast) setup are provided on these clusters:\
W&M's Sciclone: 
```
/sciclone/data10/whuang07/NWM/DEM/DEM/
```
VIMS' James: 
```
/ches/data10/whuang07/Case1/DEMs/DEM_pre/DEM/
```
Stampede2: 
```
/work/06923/wendy611/stampede2/NWM/DEM/DEM/
```
Corral3 (DesignSafe): 
```
/gpfs/corral3/repl/projects/NHERI/projects/8958936882960536041-242ac11a-0001-012/vims_noaa_archive/DEM/
```

# Steps of bathymetry loading (the order matters):
- Ocean:
> etopo1.asc
- Areas not of interest:
> set a minimum depth of 5 m globally to prevent wetting/drying (e.g., near the Caribbean islands; the areas of interest will be dealt with next)
- Areas of interest, Coastal zones:
> crm_3arcs\*, cdem13_\*, continetalus_southcarolina\*, North_Carolina_USGS_3m\*, al_ll\*, nc_ll\*, fl_ll\*, gulf_1\*, gulf_3\*, ge_ll\*, sc_ll\*, cb_ll\*, db_ll\*, new_england\*
- Regions that have DEM issues: 
> At present, we have identified three regions (Bergen Point and Sabine Pass and Washington) where the best DEMs we have show clogged channels which contradicts NOAA navigation charts. This has led to excessive blockage of tides in these regions. Therefore, we have used the navigation charts and our best judgement as DEMs in those regions (BergenPoint.reg, SabinePass.reg, Washington_3.reg). In the future, there regions will be removed from the bathymetry loading script once better DEMs are available.  

# Script
The DEMs in each batch can be loaded in parallel by a fortran script:
```
[SCHISM GIT]/src/Utility/Pre-Processing/NWM/Load_Bathy_mpi/interpolate_depth_structured2_mpi.F90
```
Follow the steps in
```
[SCHISM GIT]/src/Utility/Pre-Processing/NWM/Load_Bathy_mpi/README
```
For the participants of the NOAA 2021-02 workshop, you can try this if you have access to TACC's Stampede2, where the DEMs are provided; if not, feel free to try it on your home cluster with your own DEMs. You can contact Dr. Wei Huang (whuang@vims.edu) for any questions.

The compile command on Stampede2 is: 
```bash
mpiifort -O2 -mcmodel=medium -o interpolate_depth_structured2_mpi interpolate_depth_structured2_mpi.f90
```
