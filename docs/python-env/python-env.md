---
layout: default
title: Python Environment
nav_order: 70
permalink: docs/python-env
---

# Overview
The VIMS group is migrating all pre/post-precessing tasks to Python-based tools,
e.g., [PySCHISM]({{ site.baseurl }}{% link docs/PySCHISM/PySCHISM.md %}) and [Pylibs]({{ site.baseurl }}{% link docs/Pylibs/Pylibs.md %}).
Setting up a python environment enables you to take advantage of these readily-made tools.

We recommend using conda or [mamba](https://github.com/mamba-org/mamba) to manage your python environment.

# Example on W&M's Sciclone
## Install Mamba from scratch
- Select a subcluster (femto is the latest)

- Get the installer from mambaforge:

`wget https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-Linux-x86_64.sh`

Under your home directory:

`./Mambaforge-Linux-x86_64.sh`

"chmod +x" if necessary; yes to all installer questions

- Set Mamba base environment to autoload upon logon
Append the content of this file

`/sciclone/home10/feiye/conda_init_rc`

to the end of your

`~/.cshrc`

This step is required because Mamba does not have the option to write the '.cshrc' directly.

Add one more line 'conda activate base' at the end of the .cshrc file.
so everytime you login you are in your base environment 

## Install tool set:
- [PySCHISM]({{ site.baseurl }}{% link docs/PySCHISM/PySCHISM.md %}) 
- [Pylibs]({{ site.baseurl }}{% link docs/Pylibs/Pylibs.md %}) 
