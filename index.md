---
layout: default
title: Home
nav_order: 1
description: "Tutorials on SCHISM applications and utility scripts"
permalink: /
---

# SCHISM tutorials
{: .fs-9 }

Tutorials on SCHISM applications and utility scripts
{: .fs-6 .fw-300 }

[Get started now](#preparation){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [Contribute to the tutorial on GitHub](https://github.com/feiye-vims/schism-tut){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Before you start
This tutorial site is under construction.

The purpose of this site is to provided a tutorial easy for user-contribution and regular update, so that it can keep up with the rapid developement of the SCHISM model.

Please visit the [SCHISM website](https://schism.wiki) and read the [SCHISM Manual](http://ccrm.vims.edu/schismweb/SCHISM_v5.9-Manual.pdf) first.
Also check the [user forum](http://ccrm.vims.edu/w/index.php/Main_Page) and see if your questions have already been answered.
There are past tutorials in the forum too.

---

## Preparation

### Aquire the SCHISM source code

The recommended way to get the latest SCHISM code is via Github at [schism-dev/schism](https://github.com/schism-dev/schism).
On the UNIX command line, this is:
```bash
git clone https://github.com/schism-dev/schism.git [some_dir_name]
```
or
```bash
git clone git@github.com:schism-dev/schism.git [some_dir_name]
```
The SCHISM source code will be cloned into a folder called "schism/" by default if you don't specify "some_dir_name".

The full path to "schism/" or [some_dir_name] will be referred to as [schism_git_dir] throughout this tutorial.
You can get the full path of SCHISM Git repo on your computer by
```bash
readlink -f [some_dir_name]
```

### Compile SCHISM
Cmake is the recommended tool to compile the SCHISM executable and the utility scripts.

---

## Contributing

You are welcome to add a tutorial of your own SCHISM application by committing to the [Github repository of this tutorial](https://github.com/feiye-vims/schism-tut).
The VIMS team will quality-check the new additions periodically.

We recommend that you use [markdown](https://www.markdownguide.org/cheat-sheet/) instead of HTML to
(1) accomodate for the people who are not familiar with HTML, so that everybody can make changes to or build on your tutorial;
(2) keep the source code and page layout simple for the VIMS team to check.

For more details, check the guidance in [Share your own tutorials]({{ site.baseurl }}{% link docs/share-your-own-tutorials/share-your-own-tutorials.md %}).


