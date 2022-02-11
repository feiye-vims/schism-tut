---
layout: default
title: Q&A
parent: Miscellaneous
nav_order: 1
permalink: docs/misc/QA
---

# Questions and answers

## Ramping of atmospheric forcing
Q:<br>
When SCHISM run begins with "hotstart", does it still do ramping up of wind if nrampwind=1?

A:<br>
There are two hotstart modes in SCHISM:

-ihot=1: forecast mode, with time reset as t=0. In this case, nrampwind and other ramp flags will ramp up the forcings

-ihot=2: hindcast mode, and the run basically restarts from previous run, so nramp\* etc will do exactly the same thing as the original run.
If the restart time is beyond the ramp period, forcing is at full strength.
If not, the forcing will be ramped up.

  
