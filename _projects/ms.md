---
title: Programmable Memory Hierarchy for Memory Services
tag: ms
image:
---

This project is developing a new system architecture
that lets applications *re-program the memory hierarchy*
to specialize its operation.
We are developing a new data-centric model called _Memory Services_
and new hardware to give programmers unprecedented control over the memory hierarchy.

We have begun by developing several exemplar services
to demonstrate the potential of Memory Services and learn their common design patterns.
Thus far, we have built Memory Services that improve performance and energy-efficiency by 2X on
challenging irregular computations (e.g., graph processing and linked data structures).
We are now building a programmable memory hierarchy called _Livia_ to support these services, as well as many others.
Livia distributes reconfigurable *Memory Service Engines* throughout the memory hierarchy,
which can perform computation or other actions within the memory hierarchy as demanded by each Memory Service.
