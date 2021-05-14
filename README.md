# OSAB Docs

Add this to the top of every page and make sure to edit it for each page!
```
---
title: [Title]                    # This is the page title
has_children: [true | false]      # This makes it its own dropdown section in the navbar
parent: [Title of parent]         # Set this as the section it is in if you want the page to be under a section
parents:                          # Set this as the section its section is in if its section is in a section (ex: Vessels->Miine->Firmware you would set Vessels as the grand parent for Firmware) [The order is important. Start with the parent at the top and go down in order]
  - [Title of parent]
  - [Title of grand parent]
  - [Title of great grand parent]
  - [etc]
nav_order: [Number]               # This is the page's possition in the nav bar or navbar section
permalink: [Path]                 # This is the link of the page (ex: /vessels/miine/ would be https://docs.osab.xyz/vessels/miine/)
---
```
For example:
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
