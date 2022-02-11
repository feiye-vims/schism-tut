---
layout: default
title: Pylibs
nav_order: 72
permalink: docs/Pylibs
---

# Overview
Pylibs, written by Dr. Zhengui Wang, is a Python library for pre/post-processing SCHISM runs and other daily tasks.
The package is available on GitHub: [pylibs](https://github.com/wzhengui/pylibs).


At the moment, it is mainly used internally by the VIMS group and not published on pypi.
However, the usage and the installation are straightforward:

- Latest version:

`pip install git+https://github.com/wzhengui/pylibs.git`

If "pip" fails to resolve the dependencies of the pre-requisites, use conda or mamba to install "pip matplotlib numpy scipy pandas pyproj netCDF4 mpi4py ipython" first. 

- Latest stable (tag) version on pypi-test:

`pip install --index-url https://test.pypi.org/simple/ --extra-index-url https://pypi.org/simple pylibs4schism==0.1.10`

If "mpi4py" fails to install, use conda or mamba to install it first:

`mamba install mpi4py`


A tutorial in the format of the Jupter Notebook is available here: [pylibs tutorial](https://colab.research.google.com/drive/1X_plhKRxgjBStbv2xMQgGgE_i8Mf2Bnm).
The recommended viewing tool is Google Colab, which can be installed as an app in the Google Chrome browser.
