---
title: Smart Caching at Datacenter Scale
tag: caching
image: images/lhd.png
summary: Datacenter applications must serve petabytes of data at high throughput and minimum cost. This project merges caching theory with systems to build smart, efficient, and low-cost caching solutions for the datacenter.
---

Datacenter applications at companies like Google, Facebook, Microsoft, etc serve enormous workloads consisting of petabytes of data.
Caching plays a critical part in serving these workloads at high throughput and low cost,
but datacenter's massive scale introduces many new challenges for caching systems.
To keep cost low, datacenter caches must combine different technologies (DRAM, NVM, flash) with different cost and performance,
as well as other unique properties like limited write-endurance in flash and NVM.

This project aims to build smart, high-performance, and low-cost caching systems for datacenter applications.
We are focused on both theory and practice.
On the theory side, we extend and apply caching theory to address the new challenges at datacenter scale.
On the practical side, we are designing and implementing caching systems that combine lessons from theory
with engineering insights to make the best use of diverse technologies.

The above image sketches how LHD (NSDI'18) implements a theoretically-grounded eviction policy based on Bayesian inference
in a design inspired by recent, high-associativity cache designs for processors based on statistical sampling.
We are currently building caching systems that make efficient use of flash-based SSDs for very small objects,
and co-designing caches with the backing storage system to optimize end-to-end cost across the datacenter.

Checkout our frequent collaborators on the [PDL caching project](https://www.pdl.cmu.edu/CILES/index.shtml).
