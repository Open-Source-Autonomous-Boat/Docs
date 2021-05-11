# OSAB Docs

Add this to the top of every page
The has_children, parent, and grand_parent thing is basicly how you make folders/dropdowns/sections in the sidebar
```
---
title: Granchild of Test
has_children: true
parent: Child of Test
grand_parent: Test
nav_order: 1
permalink: /bar/
---
```
Be sure to remove the unneed parts and edit it
For example, if i have a page named Miine that should be under the Vessels section and is its own section I would do this:
```
---
title: Miine 
has_children: true          # this line makes it its own section
parent: Vessels             # this line makes part of the Vessels section
nav_order: 1                # this makes it the first link under the Vessels section
permalink: /vessels/miine/  # this makes its link https://docs.osab.xyz/vessels/miine/
---
```
