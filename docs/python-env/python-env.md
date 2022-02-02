---
layout: default
title: Python Environment
nav_order: 70
permalink: docs/python-env
---

# Overview
The VIMS group is migrating all pre/post-precessing tasks to Python-based tools,
e.g.,
- [PySCHISM]({{ site.baseurl }}{% link docs/PySCHISM/PySCHISM.md %}) 
and
- [Pylibs]({{ site.baseurl }}{% link docs/Pylibs/Pylibs.md %}) 
. Setting up a python environment enables you to take advantage of these readily-made tools.

We recommend using conda or [mamba](https://github.com/mamba-org/mamba) to manage your python environment.

# Example on W&M's Sciclone
## Install Mamba
Select a subcluster (femto is the latest) 
Copy link to install Mamba from ( ) 
On sciclone: wget ‘link address’
In home directory: ./Mamba…sh 
Yes to conda install 

- Set Mamba base environment to autoload upon logon
cp /sciclone/home10/feiye/conda_init_rc to your home dir 
copy this file to the end of your .cshrc file 
Also at the end of the .cshrc file add ‘conda activate base’ 
so everytime you login you are in your base environment 
If you somehow get out of base env, use: conda activate base 

## Install tool set:
- [PySCHISM]({{ site.baseurl }}{% link docs/PySCHISM/PySCHISM.md %}) 
- [Pylibs]({{ site.baseurl }}{% link docs/Pylibs/Pylibs.md %}) 
