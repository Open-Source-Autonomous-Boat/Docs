# OSAB Docs

Add this to the top of every page and make sure to edit it for each page!
```
---
title: [Title]                            # This is the page title
has_children: [true | false]              # This makes it its own dropdown section in the navbar
parent: [Title of parent]                 # Set this as the section it is in if you want the page to be under a section
grand_parent: [Title of grand parent]     # Set this as the section its section is in if its section is in a section (ex: Vessels->Miine->Firmware you would set Vessels as the grand parent for Firmware)
nav_order: [Number]                       # This is the page's possition in the nav bar or navbar section
permalink: [Path]                         # This is the link of the page (ex: /vessels/miine/ would be https://docs.osab.xyz/vessels/miine/)
---
```
For example, if I have a page named Miine that should be under the Vessels section and is its own section I would do this:
```
---
title: Miine 
has_children: true          # this line makes it its own section
parent: Vessels             # this line makes part of the Vessels section
nav_order: 1                # this makes it the first link under the Vessels section
permalink: /vessels/miine/  # this makes its link https://docs.osab.xyz/vessels/miine/
---
```
