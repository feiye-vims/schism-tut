---
layout: default
title: Atmospheric forcing (sflux)
parent: Compound Flooding Models
permalink: docs/compound-flood/sflux
---

# Overview

Under your run directory, create a subfolder ($your_run_dir/sflux/), which takes 4 types of files:
1. **sflux_inputs.txt**\
this asci file is a namelist; see this [example](http://ccrm.vims.edu/yinglong/feiye/Workshop_20190701/TEMP/Doc/sflux_inputs.txt). In practice, all parameters may be omitted and the default values set in the SCHISM code will be used, e.g., see the [sflux_inputs.txt](http://ccrm.vims.edu/yinglong/feiye/Workshop_20190701/Delaware/sflux/sflux_inputs.txt) for the Delaware Bay setup.
1. **sflux_air_[dataset_number].[stack_number].nc**\
wind speed at 10 m above MSL (u,v), air temperature and pressure and specific humidity;
1. **sflux_prc_[dataset_number].[stack_number].nc**\
precipitation
1. **sflux_rad_[dataset_number].[stack_number].nc**\
downward long and short (solar) wave radiation fluxes

# Make your own sflux files

You have to convert your atmospheric datasets into SCHISM's sflux format. You can use the netcdf files in this [folder](http://ccrm.vims.edu/yinglong/feiye/Workshop_20190701/Delaware/sflux/) as a reference of the file format. In addition, these Matlab scripts can serve as guides on how to write netcdf files in SCHISM's sflux format:
```
[SCHISM_Git_dir]/src/Utility/Sflux_nc/dwd2sflux.m
[SCHISM_Git_dir]/src/Utility/Sflux_nc/CFSR/
```
The number of time records in each netcdf file is flexible, as long as the files under each type is sequentially named with 4-digit integers, e.g.:
```
sflux_air_1.0001.nc, sflux_air_1.0002.nc, sflux_air_1.0003.nc, sflux_air_1.0004.nc, etc.
```
It is possible to use 2 datasets for each type, e.g.:
```
sflux_air_1.0001.nc, sflux_air_1.0002.nc, sflux_air_1.0003.nc, sflux_air_1.0004.nc, etc.
```
and
```
sflux_air_2.0001.nc, sflux_air_2.0002.nc, sflux_air_2.0003.nc, sflux_air_2.0004.nc, etc.
```
In this case, sflux_air_2.\*.nc is prioritized. This is useful when you have a high-quality dataset (set as sflux_air_2.\*.nc) but with spatial gaps; the low-quality dataset (set as sflux_air_1.\*.nc) will be used to fill in the gaps. The grid in sflux_air_2.\*.nc can differ from that in sflux_air_1.\*.nc.
The sflux folder needs to be present under your run directory. Since the file sizes are usually large, it is recommended to do a symbolic link.


# Limitations on 2D

A limitation of a 2D model is that it cannot directly read precipitation from "sflux/". It is not a straightforward change in the SCHISM code, so we use a pre-processing script to convert precipitation from sflux to sources. This is similar to how NWM streamflows are injected into the domain, except that the injection points are no longer constrained to the land boundary. In practice, we usually manually define a region of interest (e.g., the region affected by the hurricane) and only include
the preciptation within it.
You can find a group of Matlab scripts here:
```
[SCHISM_Git_dir]/src/Utility/Pre-Processing/NWM/Sflux2Source/
```
, which convert precipitation from sflux (atmosphere) to volume sources injected at grid elements, then merge them with the sources/sinks from NWM streamflows if any. See the README inside the script folder for usage.

There is another set of scripts based on NCL:
```
[SCHISM_Git_dir]/src/Utility/Pre-Processing/NWM/Sflux2Source_ncl/
```
, which may be more efficient than Matlab.
Note that these two sets of scripts may give slightly different results due to the different interpolation methods used.

Since Jan 24, 2021 (schism-dev/schism, hash 3576c9), you can use netcdf format to specify sources/sinks when if_source=-1 in param.nml. In this case, a single netcd file "source.nc" is used instead of "source_sink.in", "vsource.th", "vsink.th", and "msource.th". You can refer to this Matlab [script](http://ccrm.vims.edu/yinglong/feiye/Workshop_20190701/TEMP/Doc/gen_source.m) for the format of "source.nc".


# Note on the Irene Period

The sflux used for the Delaware Bay model during the Irene (2011) period is based on an ECMWF product shared with us through private communication. This product is of higher resolution than the ECMWF's public-domain products (e.g., [ERA5](https://www.ecmwf.int/en/forecasts/datasets/reanalysis-datasets/era5)), but only available to us during the Irene (2011) period.
