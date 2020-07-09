---
title: Software-Defined Memory Hierarchy
tag: sdm
image: images/jumanji.png
---

This project dramatically improves multicore performance and energy-efficiency by reducing data movement.
Traditional memory hierarchies force significant unnecessary data movement because of their rigid organization,
which is fixed at design time and does not adapt to how different applications access data.
In constrast, *Software-Defined Memory Hierarchies* dynamically adapt themselves to give each application the memory hierarchy it wants.
This is done transparently to applications using simple hardware and a lightweight software runtime.

We are now developing Software-Defined Memory Hierarchies for heterogeneous applications and architectures.
On the application side, we are exploring how Software-Defined Memory Hierarchies can support applications with diverse throughput, security, and tail-latency requirements.
On the architecture side, we are exploring how Software-Defined Memory Hierarchies can ease the adoption of accelerator-rich SoCs by making more efficient use of on-chip memories and by defining a common interface to shared memory.
