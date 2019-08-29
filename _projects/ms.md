---
title: Programmable Memory Hierarchy for Memory Services
tag: ms
image:
---

This project is developing *Memory Services*,
a new programming model to specialize the memory hierarchy,
as well as a new system architecture to implement Memory Services.

Memory Services allow programmers to specialize the memory hierarchy to support their application in a variety of ways.
On the simpler side, applications could de-compress/compress data as it moves to/from memory using more effective, app-specific compression techniques.
Getting more complex, applications can implement complex data structure operations within the memory hierarchy,
or even completely change how the memory hierarchy functions to specialize for a particular application domain.

We aim to demonstrate the potential of the Memory Service model by developing exemplar services and by designing a programmable cache hierarchy to support a wide range of services.
This architecture distributes new, reconfigurable *Memory Service Engines* throughout the memory hierarchy to give applications unprecedented control over data movement.
We have begun by developing services for graph processing and other irregular data structures.