---
layout: post
title: Symbolic Graph Reasoning Meets Convolutions
author: RyuTian
---

The last author of this paper is Eric P. Xing, which is my idol. And i have hounor to see him in Sanya early in this year. This paper is the newest work advanced by him and published on Neurips 2018.

![title](../images/sgr-1.png)

## Symbolic Graph Reasoning Meets Convolutions
-----
The proposed method is illustrated below:

![title](../images/sgr-2.png)

It is composed of three parts, we will dig out these components one by one.

### Local-to-Semantic Voting Module

<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML"> </script>

#### Purpose:

Given local feature tensors from convolution layers, our target is to leverage global graph Reasoning to enhance local features with external structured knowledge.

#### How to do:

1. First summarize the global information encoded in local features into representations of Symbolic nodes.

This module aims to produce visual representations $$ H^{p s} \in \mathbf{R}^{M \times D^{c}} $$ of all $$ M=|\mathcal{N}| $$ symbolic nodes using $$ X^{l} $$

$$ H^{p s}=\phi\left(A^{p s}, X^{l}, W^{p s}\right) $$

$$ X^{l} \in \mathbf{R}^{H^{l} \times W^{l} \times D^{l}} $$ represents the feature tensor after $$ lth $$ concolution layer as the module inputs, where $$ H^{l} $$ and $$ W^{l} $$ are height and weight of feature maps while $$ D^{l} $$ is the channel number.
