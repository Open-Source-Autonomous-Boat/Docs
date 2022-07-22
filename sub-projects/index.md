---
title: Sub-Projects
nav_order: 1
permalink: /sub-projects/
---

# Sub-Projects

OSAB is a big project that is made up of many different pieces and technologies. As such, it sometimes make sense to partition the overall project into smaller projects that are maintained individually. For example, due to the complexity of the code that is required to run and control the vessels, it makes sense to maintain a fully featured and configurable firmware framework rather than rewritting the code for each unique vessel. This also has other advantages such as allowing our work to be more applicable in other fields like underwater drones through firmware contributions from the open source community.

Currently we have not determined what parts of the project should be maintained this way but some possable projects could include:

- A vessel firmware framework
- An embedded linux distribution targeted towards autonomous vehicles
- A low power SCB targeted towards controlling robotics and autonomous vehicles
- A protocol for autonomous vehicle control and communication
- A protocol for communication between onboard devices/computers (built on top of CAN Bus)
- A compact file format for storing missions/instructions for autonomous vessels
