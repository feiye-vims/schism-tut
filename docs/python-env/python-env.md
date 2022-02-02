---
layout: default
title: Python Environment
nav_order: 70
permalink: docs/python-env
---

# Overview
The VIMS group is migrating most pre/post-precessing utiliies to Python-based tools,
e.g., [PySCHISM]({{ site.baseurl }}{% link docs/PySCHISM/PySCHISM.md %}) and [Pylibs]({{ site.baseurl }}{% link docs/Pylibs/Pylibs.md %}).
Setting up a python environment enables you to take advantage of these readily-made tools.

We recommend using conda or [mamba](https://github.com/mamba-org/mamba) to manage your python environment.

# Example for W&M's Sciclone
## Install Mamba from scratch
We don't recommend using the conda module provided by SciClone, because you may run into permission issues or get confused with different conda versions on different subclusters.

Follow these steps to set up Mamba from scratch:
- Select a subcluster (femto is the latest; the environment will be usable on all subclusters after installation)

- Get the installer from mambaforge:

`wget https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-Linux-x86_64.sh`

Install (e.g., under your home directory):

`./Mambaforge-Linux-x86_64.sh`

`chmod +x Mambaforge-Linux-x86_64.sh` if necessary; yes to all installer questions



## Autoload Mamba base environment upon logon

- Append the content of this file `/sciclone/home10/feiye/conda_init_rc` to the end of your `~/.cshrc`
This step is required because Mamba does not have the option to write the '.cshrc' directly.

- Add one more line 'conda activate base' at the end of the .cshrc file.
so everytime you login you are in your base environment 



## Install tool set

### Install ipython

`mamba install ipython`


### Install [PySCHISM]({{ site.baseurl }}{% link docs/PySCHISM/PySCHISM.md %}) 

Test Installation: type `ipython`, then in ipython: `from pyschism.mesh import Hgrid`

If warnings appear, you can try these steps to fix them (or leave them be): 

`pip uninstall shapely`

`conda install -c conda-forge- geos`

`pip install shapely --no-binary shapely`


### Install [Pylibs]({{ site.baseurl }}{% link docs/Pylibs/Pylibs.md %}) 

Test Installation: type `ipython`, then in ipython: `import pylib`
