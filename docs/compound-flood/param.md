---
layout: default
title: Parameters (param.nml)
parent: Compound Flooding Models
nav_order: 1
permalink: docs/compound-flood/param
---

# Overview
When making a SCHISM run from scratch, always start from the sample param.nml in GIT:
```
[SCHISM_Git_dir]/sample_inputs/param.nml
```
A brief description of each parameter is provided in param.nml.
There are three groups of parameters in param.nml, defined by: "CORE", "OPT", and "SCHOUT", namely "core", "optional", and "schism outputs".


# Important parameters for simulating compound flooding
- **2D setup**:

  - CORE: ibc, ibtp, rnday, dt, nspool, ihfskip
  - OPT: start_*, utc_start, ics, nramp, if_source, nramp_ss, nchi, ic_elev, nws, nrampwind, itur, iflux

- **3D setup**:

  - CORE: ibc, rnday, dt, nspool, ihfskip
  - OPT: start_*, utc_start, ics, nramp, if_source, nramp_ss, nchi, ic_elev, nws, nrampwind, itur, iflux, itr_met, indvel, ihorcon, ishapiro, ihconsv, isconsv, i_hmin_airsea_ex, hmin_airsea_ex

Please refer to the sample param.nml for their meanings and usages.
