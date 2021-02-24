---
layout: default
title: Share your own tutorials
nav_order: 90
permalink: docs/share-your-own-tutorials
---

# Become a collaborator
All SCHISM users are welcome to share their own cases to this tutorial site.

All contributions are appreciated, be it
as simple as a suggestion on the existing procedure,
or a pre/post precessing script,
or something more complex like the [Compound flooding model]({{ site.baseurl }}{% link docs/compound-flood/compound-flood.md %}).

Please contact Fei Ye (feiye@vims.edu) to be included as a collaborator of the [Github repository](https://github.com/feiye-vims/schism-tut).

# Adding contents

## Location to put your stuff

To add a new tutorial or a new page in the existing tutorials, you only need to worry about the "docs/" folder,
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
Remember to set a title at the beginning of the \*.md file.
You don't need to worry about the "nav_order", we will periodically re-order the new tutorials.
For example, the beginning lines of the source code of the current page (`docs/making-your-own-tutorials.md`) look like:
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
1. At the beginning of "your_tutorial.md": set an appropriate title; assign any value to "nav_order"; set "has_children: true". For example,
```markdown
---
layout: default
title: Your Tutorial
nav_order: 30
has_children: true
permalink: docs/your_tutorial
---
```
Note that "your_tutorial.md" shares the same name as your tutorial folder.
This is a good place to put a summary of your tutorial.
See the summary page of [Compound flooding model]({{ site.baseurl }}{% link docs/compound-flood/compound-flood.md %}) and its source code (`docs/compound-flood/compound-flood.md`) for an example.

2. Add a \*.md file for each page of your tutorial. Set the "parent" to be the same as your tutorial's title in the previous step, for example:
```markdown
---
layout: default
title: Horizontal grid in CPP
parent: Your Tutorial
nav_order: 1
permalink: docs/your_tutorial/page_1/
---
```
Here, the "nav_order" only has local effect under "Your Tutorial", and you should assign an appropriate value to each of your tutorial pages.
You can use the source code of `docs/compound-flood/param.md` as a template.

## Minor edits
If you need to do some minor edits on the existing pages of a tutorial, the easiest way is probably directly editing the source code on Github's webpage.
But we do ask you to provide a brief and sensible commit message.

## Linking your existing tutorial

You are welcome to provide a link to your existing online tutorial.
You can follow the steps in [Short tutorial](#short-tutorial), provide a brief introduction and make an [external link](#links) to your online tutorial.

## Links
If you want to link to a content within this tutorial, use the syntax in the following example:
```
{% raw %} [Compound flooding model]({{ site.baseurl }}{% link docs/compound-flood/compound-flood.md %}) {% endraw %}
```

The external links are easier, e.g.:
```markdown
[Markdown syntax](https://www.markdownguide.org/cheat-sheet/)
```

# Markdown
A quick reference of the [Markdown syntax](https://www.markdownguide.org/cheat-sheet/).

# More features
If you need advanced features for your tutorial page, you can use some HTML syntax in your \*.md files and check the usage of the Jekyll theme of ["Just the Docs"](https://github.com/pmarsceill/just-the-docs).
However, we recommend that you keep the page layout as simple as possible.

