---
title: Software-Defined Cache Hierarchy for Multicore Processors
tag: sdm
image: images/jumanji.png
summary: This project dynamically re-organizes the large, distributed shared cache in modern multicore processors to keep applications' data as close as possible, letting applications meet their goals with minimal data movement.
---

This project dramatically improves multicore performance and energy-efficiency by reducing data movement.
Traditional memory hierarchies force significant unnecessary data movement because of their rigid organization,
which is fixed at design time and does not adapt to how different applications access data.
In constrast, *Software-Defined Memory Hierarchies* dynamically adapt themselves to give each application the memory hierarchy it wants.
This is done transparently to applications using simple hardware and a lightweight software runtime.

We are now developing Software-Defined Memory Hierarchies for heterogeneous applications and architectures.
On the application side, we are exploring how Software-Defined Memory Hierarchies can support applications with diverse throughput, security, and tail-latency requirements.
On the architecture side, we are exploring how Software-Defined Memory Hierarchies can ease the adoption of accelerator-rich SoCs by making more efficient use of on-chip memories and by defining a common interface to shared memory.

The above image shows how Jumanji (MICRO'20) allocates shared cache banks in a multicore among different virtual machines (VMs), represented by different colors.
Jumanji ensures that no two VMs share a cache bank (to eliminate security vulnerabilities)
and allocates banks so that each app meets its goals (e.g., maximizing raw performance or keeping tail latency below some threshold).
Jumanji does this while keeping apps' data as physically close as possible within the multicore, minimizing data movement.