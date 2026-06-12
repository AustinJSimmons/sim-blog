---
title: 'SIM-GPU Series: Fundamental Components of Modern GPUs'
description: 'The SIM-GPU series is about learning the architecture of modern GPUs from scratch.'
pubDate: 'Jun 19 2026'
heroImage: '../../assets/blog-placeholder-2.jpg'
---

## Motivation

The motivation of this article is to list and explain all the essential
components of modern GPUs. This list and accompanying explanations will
motivate our simplified modern GPU design/simulation. By the end of this
article I hope to give myself and the reader a basic understanding of
how modern GPUs function.

We will cover the following:

1. What does a modern GPU need to be capable of doing at a baseline? (Functionality)
2. How do modern GPUs accomplish these things? (Components)
3. What is the input/output path through these components? (Data paths)
4. What does our GPU design NEED to include based on desired functionality?
