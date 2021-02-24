---
layout: default
title: Share your own tutorials
nav_order: 90
permalink: docs/share-your-own-tutorials
---

# Become a collaborator
All SCHISM users are welcome to share their own cases on this tutorial site.

All contributions are appreciated, be it
as simple as a suggestion on the existing procedure,
or a pre/post precessing script,
or something more complex like a model setup.

Please contact Fei Ye (feiye@vims.edu) to be included as a collaborator of the [Github repository](https://github.com/feiye-vims/schism-tut).

# Adding contents

## Location to put your stuff

To add a new tutorial or a new page in the existing tutorials, you only need to worry about the "docs/" folder:
```
docs/
├── compound-flood
│   ├── compound-flood.md
│   ├── hgrid_cpp.md
│   └── workflow_2d_ecgc.png
├── share-your-own-tutorials
│   ├── share-your-own-tutorials.md
│   └── edit.png
```
, in which each topic consists a sub-folder.

## Adding a new tutorial

Make a new folder (e.g., "your_tutorial") under "docs/" and make a new file (e.g., "your_tutorial.md") under that folder.
```
docs/
├── compound-flood
│   ├── compound-flood.md
│   ├── hgrid_cpp.md
│   └── workflow_2d_ecgc.png
├── your_tutorial
│   └── your_tutorial.md
├── share-your-own-tutorials
│   ├── share-your-own-tutorials.md
│   └── edit.png
```
Note that "your_tutorial.md" shares the same name as your tutorial folder.

### Short tutorial

- If your content is short enough to fit in a single page, you can put all texts in "your_tutorial.md" and any additional materials (e.g., "your_tutorial_figure.png") under the same folder ("your_tutorial/").
Remember to set a title at the beginning of "your_tutorial.md".
You don't need to worry about the "nav_order", we will periodically re-order the new tutorials.
For example, the beginning lines of the source code of the current page (`docs/share-your-own-tutorials/share-your-own-tutorials.md`) look like:
```markdown
---
layout: default
title: Share your own tutorials
nav_order: 90
---
```

### Long tutorial

- If you need multiple pages for your tutorial, "your_tutorial.md" is a good place to put a summary of your tutorial.
See the summary page of [Compound flooding model]({{ site.baseurl }}{% link docs/compound-flood/compound-flood.md %}) for an example.
Then, add other pages and additional materials under the same folder like:
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
├── share-your-own-tutorials
│   ├── share-your-own-tutorials.md
│   └── edit.png
```
Finally, you need to specify the parent and children relationship:
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
You can use `docs/compound-flood/compound-flood.md` as a template.
1. In the \*.md files of other pages, set the "parent" to be the same as your tutorial's title in the previous step, for example:
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
You can use `docs/compound-flood/param.md` as a template.

## Adding a new page to an existing tutorial
This is similar to adding things in a [Long tutorial](#long-tutorial), just remember to set a parent at the beginning few lines of your newly added page (\*.md).

## Minor edits
If you need to do some minor edits on the existing pages of a tutorial, the easiest way is probably directly editing the source code on Github's webpage.
Click the link (
<img src="{{ site.baseurl }}{% link docs/share-your-own-tutorials/edit.png %}" alt="edit" width="200"/>
) at the bottom of any page will lead you to the source code of that page in the Git repo.
But we do ask you to provide a brief and sensible commit message.

## Linking your existing tutorial

You are welcome to provide a link to your existing online tutorial.
You can make it as a single-page short tutorial, provide a brief introduction, then make an [external link](#links) to your online tutorial.

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
If you need advanced features for your tutorial page, you can use some HTML syntax in your \*.md files and check the usage of the Jekyll theme ["Just the Docs"](https://github.com/pmarsceill/just-the-docs).
However, we recommend that you keep the page layout as simple as possible.

