---
title: Polymorphic Cache Hierarchy
tag: ms
image: images/livia.png
summary: This project is developing a "polymorphic" memory hierarchy that can be re-programmed by applications to significantly improve performance and efficiency, e.g., by moving computation to execute _within_ the cache hierarchy.
---

Current systems hide data movement behind the load-store interface,
and software's lack of control over data movement is the root of many inefficiencies.
To address this inefficiency, many have proposed specialized hardware.
But specialized hardware is very expensive to design, verify, and build,
and each new specialization is disruptive across the system stack.

We argue that the hardware-software interface is the actual problem,
and specialized hardware is usually unnecessary.
A ***Polymorphic Memory Hierarchy*** provides a much richer interface for data movement,
letting software optimize data movement itself on general-purpose hardware.
This project spans hardware, software, and compilers.

_Livia_ was the first to enable data-centric computation throughout the memory hierarchy.
Livia accelerates task-parallel programs by migrating tasks and data to location in the memory hierarchy
that minimizes overall data movement.
Livia programs are written using a continuation-passing API as a graph of dynamically generated tasks.
Tasks are written as functions following a standard signature,
and to launch a task programs simply `invoke` the appropriate function on the relevant data.
Livia hardware automatically then finds the data and executes the function nearby.
Functions can return values to the caller by fulfilling a future.

The above diagram shows how Livia executes tasks within the memory hierarchy.
Livia hardware automatically migrates data to settle at its "natural" location in the memory hierarchy according to how its used,
and then dynamically schedules task execution on the closest Memory Service Engine (see below) to maximize efficiency.
Livia can improve performance by 2X on challenging irregular algorithms and data structures, which have proven difficult to accelerate.

_täkō_ extends the programming interface to let software fully observe and control data movement.
We observe that a key missing feature in current systems is the ability to perform short computations when data moves.
täkō programs can register callbacks on certain address ranges
so that software is invoked when data in this range moves.
Specifically, täkō programs can register callbacks to execute on cache misses, evictions, or writebacks.

Microarchitecturally, Polymorphic Cache Hierarchies distribute small "Memory Service Engines" (MSEs)
on each tile of a multicore.
These engines comprise hardware scheduling logic and a dataflow fabric that executes tasks efficiently.
We are prototyping this design in RTL, including a detailed design of the dataflow fabric so that
it execute multiple concurrent tasks at low hardware overhead.
