---
layout: default
title: Install SCHISM on Ubuntu
parent: Miscellaneous
nav_order: 1
permalink: docs/misc/install_schism_on_ubuntu
---

# Experience shared by Behzad Nazari
On an Ubuntu 20. 04 with an Intel-Core i7 processor, I installed the following packages:

gcc, gfortran, libnetcdff-dev, libscalapack-mpich2.1, build-essential
 
I cloned Jaime Calzada’s git at https://github.com/jreniel/schism_deploy_v5.9.0.git.
Since I used his instructions and because it worked, I didn’t go back to get the main SCHISM git.
I navigated to the main folder and made the build folder:
```
  $ cd schism_v5.9.0/
  $ mkdir build
  $ cd build
  $ cmake ../src
```

Note that there were times the cmake would run successfully right away.
There were several other instances when I was installing on VMs that I couldn’t get the first cmake command to work.
In those cases, I used the error messages and the  CMakeCache file created to see which compilers might have been flagged with NOTFOUND and fixed them after using “whereis” to find gcc, gfortran, mpicc, mpif90, etc.
After that, I executed the make command to get the main pschism_TVD_VL and the rest of pre- and post-processing scripts: 
```
  $ make
```
And that’s basically it. Changing the CMakeCache and repeating the make process with the other modules turned on shouldn’t cause any issues. 
