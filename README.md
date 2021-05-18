# OSAB Docs

OSAB's documentation is a GitHub pages site. It runs Jekyll and uses the [Just-The-Docs](https://pmarsceill.github.io/just-the-docs/) theme.

## Syntax
All page files are `.md` files and use GitHub's markdown syntax. You can learn it [here](https://guides.github.com/features/mastering-markdown/).

## New Pages
### Titles & naming schemes:
'file name' is the filesystem-friendly version of the page title. For example, a page titled `Boston Dynamics` will have a file name of `boston dynamics`. Because every page is identified by its title for generating the nav tree, every page needs a title and no two pages can have the same title. 
If I have two parent pages (for two vessels, for example) that both have a child `Code` page, then even though they are in different directories in the repository, the nav tree generator will get confused because it looks at the page title and will see two `Code` pages. This means that some pages need special names to avoid duplicates. In this case, we can title them `Vessel1 Code` and `Vessel2 Code` and then add their respective file name. As the file name does not affect anything but human readability and repository organization, we can even make the file name of both files `Code` as long as the titles are different.
If a page is a parent, create a new directory and name it the page's file name. Create the new page in the directory and name the file `index.md`. If a page is not a parent just create a file and name it the file name but be sure to add the `.md` file extension.

### Creating the new page:
When creating a new page, start by making a new `.md` file. Directories don't affect anything as the nav tree is defined by each file's front matter (discussed below) but we use them to keep the files organized. How our system works is if a page is a parent and has child pages you create a new directory with its file name. 

## Front Matter
Front matter is at the top of every page file and is between the two `---` markers. It holds variables that are used to create the page from the markdown file. They set things like the title, permalink, and even define the nav tree structure

Here is a template for you to use for new files.
```
---
title: [Title]                    # This is the page title
has_children: [true | false]      # This makes it its own dropdown section in the navbar
parent: [Title of parent]         # Set this as the section it is in if you want the page to be under a section
parents:                          # Set this as the section its section is in if its section is in a section (ex: Vessels->Miine->Firmware you would set Vessels as the grandparent for Firmware) [The order is important. Start with the parent at the top and go down in order]
  - [Title of parent]
  - [Title of grand parent]
  - [Title of great grand parent]
  - [etc]
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
The nav tree is defined by variables you set in the front matter of each page. These variables include `has_children`, `parent`, `parents`, and `nav_order` and while `title` is important to set the title of your page, it is also used as a page identifier in the nav tree generation system.
```
title: [Title]                    # This is the page title
has_children: [true | false]      # This makes it its own dropdown section in the navbar
parent: [Title of parent]         # Set this as the section it is in if you want the page to be under a section
parents:                          # Set this as the section its section is in if its section is in a section (ex: Vessels->Miine->Firmware you would set Vessels as the grandparent for Firmware) [The order is important. Start with the parent at the top and go down in order]
  - [Title of parent]
  - [Title of grand parent]
  - [Title of great grand parent]
  - [etc]
nav_order: [Number]               # This is the page's vertical position in the nav tree
```

### An example:
If I have a page with children called cameras and this is its location in the tree:
/Boston Dynamics/Robots/Spot/Hardware/Cameras
This is what the file would look like:
```
---
title: Cameras
parents:
  - Hardware
  - Spot
  - Robots
  - Boston Dynamics
parent: Hardware
has_children: true
nav_order: 1
permalink: /boston-dynamics/robots/spot/hardware/cameras
---
```
