# OSAB Docs

OSAB's documentation is a GitHub pages site. It runs Jekyll and uses the [pdmosses/just-the-docs@rec-nav-2](https://github.com/pdmosses/just-the-docs/tree/combination-rec-nav) theme which is a fork of [Just-The-Docs](https://pmarsceill.github.io/just-the-docs/). You can find the pull request [here](https://github.com/pmarsceill/just-the-docs/pull/462) if you want this fork to be added to the base Just-The-Docs repo

## Syntax
All page files are `.md` files and use GitHub's markdown syntax. You can learn it [here](https://guides.github.com/features/mastering-markdown/).

## New Pages
### Titles & naming schemes:
'file name' is the filesystem-friendly version of the page title. For example, a page titled `Boston Dynamics` will have a file name of `boston-dynamics`. Two top level pages can't have the same title .
If a new page is a parent, create a new directory and name it the page's file name. Create the new page in the directory and name the file `index.md`. If a page is not a parent just create a file and name it the file name but be sure to add the `.md` file extension.

### Creating the new page:
When creating a new page, start by making a new `.md` file. Directories don't affect anything as the nav tree is defined by each file's front matter (discussed below) but we use them to keep the files organized. How our system works is if a page is a parent and has child pages you create a new directory with its file name. 

## Front Matter
Front matter is at the top of every page file and is between the two `---` markers. It holds variables that are used to create the page from the markdown file. They set things like the title, permalink, and even define the nav tree structure

Here is a template for you to use for new files.
```
---
title: [Title]                    # This is the page title
parent: [Title of parent]         # Set this as the section it is in if you want the page to be under a section
ancestor: [Title of ancestor]     # If the page is a child of a page that has the same name as another page (if there are two 'code' pages, for example), set this as the title of that page's parent
nav_order: [Number]               # This is the page's vertical position in the nav tree
permalink: [Path]                 # This is the link of the page (ex: /vessels/miine/ would be https://docs.osab.xyz/vessels/miine/)
---
```

### General settings
`title` and `permalink` are important variables you can set for your page. `title` is required and you can learn more about setting this in [Titles & naming schemes](#titles--naming-schemes). `permalink` is what appears in the URL after the domain like https://osab.xyz/vessel1/code/firmware. In this example, you would set the `permalink` as `/vessel1/code/firmware`
```
title: [Title]                    # This is the page title
permalink: [Path]                 # This is the link of the page (ex: /vessels/miine/ would be https://docs.osab.xyz/vessels/miine/)
```

### Editing the nav tree:
The nav tree is defined by variables you set in the front matter of each page. These variables include `parent`, `ancestor`, and `nav_order` and while `title` is for setting the title of your page, it is also used as a page identifier in the nav tree generation system.
```
title: [Title]                    # This is the page title
parent: [Title of parent]         # Set this as the section it is in if you want the page to be under a section
ancestor: [Title of ancestor]     # If the page is a child of a page that has the same name as another page (if there are two 'tests' pages, for example), set this as the title of the closest ancestor page that does not have another page with the same name
nav_order: [Number]               # This is the page's vertical position in the nav tree
```

### An example:
If I have a page called `Cameras` and this is its location in the tree:
/Boston Dynamics/Robots/Spot/Hardware/Cameras
But there is also a second page named `Hardware`:
/Nasa/Robots/Spirit/Hardware
This is what the file would look like:
```
---
title: Cameras
parent: Hardware
ancestor: Boston Dynamics
nav_order: 1
permalink: /boston-dynamics/robots/spot/hardware/cameras/
---
```
