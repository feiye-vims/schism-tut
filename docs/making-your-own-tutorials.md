---
layout: default
title: Share your own tutorials
nav_order: 90
---

# Become a collaborator
All SCHISM users are welcome to share their own cases to this tutorial site.
All contributions are appreciated, be it
as simple as a suggestion on the existing procedure,
or a pre/post precessing script,
or something more complex like the [Compound flooding model](../compound-flood/),

Please contact Fei Ye (feiye@vims.edu) to be included as a collaborator of the [Github repository](https://github.com/feiye-vims/schism-tut).

# Adding contents

## Location to put your stuff

To add a new tutorial or a new page in the existing tutorials, you only need to worry about the "doc" folder,
which looks like:
```
docs/
├── compound-flood
│   ├── compound-flood.md
│   ├── hgrid_cpp.md
│   └── workflow_2d_ecgc.png
├── making-your-own-tutorials.md
```

## Short tutorial

If your content is short enough to fit in a single page, you can add one \*.md file (e.g., **your_tutorial.md**) under docs/, like:
```
docs/
├── compound-flood
│   ├── compound-flood.md
│   ├── hgrid_cpp.md
│   └── workflow_2d_ecgc.png
├── your_tutorial.md
├── making-your-own-tutorials.md
```
Remember to set a title and a "nav_order" in the beginning of the \*.md file.
For your new tutorial, you can use any nav_order value between 11 and 89, which may or may not be changed by the VIMS team.
For example, the beginning lines of the source code (making-your-own-tutorials.md) of this page looks like:
```markdown
---
layout: default
title: Making your own tutorials
nav_order: 90
---
```

## Long tutorial

If you need more pages for your tutorial, make a new folder (e.g., **your_tutorial/**) under docs/, like:
```markdown
docs/
├── compound-flood/
│   ├── compound-flood.md
│   ├── hgrid_cpp.md
│   └── workflow_2d_ecgc.png
├── your_tutorial/
│   ├── your_tutorial.md
│   ├── page_1.md
│   ├── a_figure_for_page_1.png
│   └── page_2.md
├── making-your-own-tutorials.md
```

Then do the following:
1. In addition to setting the  title and nav_order, set "has_children: true" at the beginning of "your_tutorial.md". For example,
```markdown
---
layout: default
title: Your Tutorial
nav_order: 30
has_children: true
permalink: docs/your_tutorial
---
```
For your new tutorial, you can use any nav_order value between 11 and 89, which may or may not be changed by the VIMS team.
Add some introduction in "your_tutorial.md". Note that this file shares the same name as the parent folder.

2. Add a \*.md file for each page of your tutorial. Set the "parent" to be the same as your tutorial's title in the previous step, for example:
```markdown
---
layout: default
title: Horizontal grid in CPP
parent: Your Tutorial
permalink: docs/your_tutorial/page_1/
---
```

## Minor changes
If you need to do some minor edits on the existing pages of a tutorial, the easiest way is probably directly editing the source code on Github's webpage.
But we do ask you to provide a brief and sensible commit message.
