---
title: 'SIM-GPU Series: Historic Evolution of GPUs'
description: 'The SIM-GPU series is about learning the architecture of modern GPUs from scratch. This one covers the difference between early 2000s GPUs and todays modern GPUs. From SIMD to SIMT and how they differ.' 
pubDate: 'Jun 12 2026'
heroImage: '../../assets/NV1.avif'
---

## Motivation

The motivation behind this article is to understand how GPU architectures evolved.
When I started the sim-gpu project, I ran into a lot of conflicting information
about how GPUs function. Depending on the time period, the underlying information
may have been outdated or not applicable to modern GPU architecture.

This article serves to help me sort through what is and isn't needed to simulate
a simple version of modern GPU architectures.

## From Gaming and Graphics to Parallel Powerhouses

When graphics cards first started popping up, they were a specialized piece of
computer hardware specifically designed to speed up the processing of vectors
in 2D/3D graphics and video games. Hence the name *Graphics Processing Unit*.
The Gaming and Graphics industries would drive most of the innovation in
parallel processing until the early 2000s.

In the early 2000s universities, labs and individuals discovered that GPUs could
be used to run complex linear algebra and matrix multiplication far faster than
CPUs. However, you would need to use graphics primitives and essentially trick
these pieces of hardware into doing anything other than just computing graphics.
People did do this but it wasn't as widely adopted. That was until 2006 when
NVIDIA released CUDA (Compute Unified Device Architecture),
then all of a sudden GPUs could explicitly be used for massive parallel
processing without the arduous task of using graphics primitives to get what
you want. This was the major paradigm shift that lead to GPUs being seen as
more than just Graphics Processing Units.

No longer tied to the graphics and video games industries as before (at least not
as much) GPUs were now being used for far more. GPGPU or general Purpose computing
on graphics processing units, while it existed before, would soon become a primary
driver behind future innovation of GPUs. Really it was just a matter of time and
exposure to more fields before GPUs would radically shift in how they operate.

Enter Ilya Sutskever, who alongside Geoffrey Hinton and Alex Krizhevsky decided
at the University of Toronto in 2012 to use GPUs for applications in Neural
Networks and thus the explosion of GPUs being used in the field of AI began to
take off.

## Changes

So what actually changed over this period?

Early GPUs relied on configurable but fixed function hardware organized in a
hardwired sequential pipeline. They had separate hardware for vertex and fragment
shading. They had highly restricted input and output, as well as extremely limited
communication between 'threads'. For example fragment shaders could only receive
input as interpolated vertices/textures and could only output data directly to
a frame buffer. Finally they focused heavily on single precision
floating point arithmetic, which was sufficient for pixel interpolation and
computing geometric vertices.

Modern GPUs (we are skipping some steps) replaced the hardwired
pipeline with a more unified architecture centered around SMs (Streaming Multiprocessors).
SMs are multi-threaded general purpose compute cores capable of running both graphic
shaders and 'compute' shaders without relying on the old traditional graphics pipeline.
Remember how we said people used to have to trick GPUs into computing things
other than graphics? Modern GPUs addressed this with the unified architecture centered
on SMs. To support this modern GPUs needed to implement a more complex memory hierarchy.
They include shared memory for communication between threads, as well as parallel
L1/L2 caches and independent memory partitions for improved latency. They also
added double precision floating arithmetic as well as standard scalar operations
for integers and bit operations.

Now as we know, early GPUs followed a rigid sequential flow. This flow was driven
directly by graphics APIs. Modern GPUs on the other hand implemented complex
control systems within SMs which enable them to dynamically schedule new workloads
for itself without CPU intervention.

Finally modern GPUs have expanded their execution units to include domain
specific hardware accelerators directly in their SMs. Think tensor cores and
RT cores.

## Takeaways

- Modern GPUs are massively parallel general compute machines.
- Modern GPUs are built to be programmable and flexible for different workloads.
- Modern GPUs have complex control units which dynamically allocate resources
  across warps/threads.
- Modern GPUs contain a memory hierarchy that enables communication between threads
  and improve latency.
- Modern GPUs support floating point arithmetic as well as standard scalar operations.

Now that I know the major differences between early and modern GPUs I should
be able to filter through information and get to a finalized high-level
design for sim-gpu.
