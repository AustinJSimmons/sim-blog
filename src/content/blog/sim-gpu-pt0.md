---
title: 'SIM-GPU Series: Historic Evolution of GPUs'
description: 'The SIM-GPU series is about learning the architecture of modern GPUs from scratch. This one covers the difference between early 2000s GPUs and todays modern GPUs. From SIMD to SIMT and how they differ.' 
pubDate: 'Jun 11 2026'
heroImage: '../../assets/blog-placeholder-1.jpg'
---

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
People did do this but it wasn't as widely adopted like it is today. That was
until 2006 when NVIDIA released CUDA (Compute Unified Device Architecture),
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
at the University of Toronto to use GPUs for applications in Neural Networks and
thus the explosion of GPUs being used in the field of AI began.

...
