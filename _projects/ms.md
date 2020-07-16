---
title: Programming the Memory Hierarchy via <i>Memory Services</i>
tag: ms
image: images/livia.png
summary: This project is developing a "polymorphic" memory hierarchy that can be re-programmed by applications to significantly improve performance and efficiency, e.g., by moving computation to execute _within_ the cache hierarchy.
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
Livia distributes reconfigurable *Memory Service Engines* (MSEs) throughout the memory hierarchy,
which can perform computation or other actions within the memory hierarchy as demanded by each Memory Service.

The above diagram shows how Livia executes tasks within the memory hierarchy for applications written as a Memory Service.
Livia hardware automatically migrates data to settle at its "natural" location in the memory hierarchy according to how its used,
and then dynamically schedules task execution on the closest MSE to maximize efficiency.
