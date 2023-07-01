---
layout: page_wo_title
title: FedCollab
description: Optimizing the Collaboration Structure in Cross-Silo Federated Learning
img: assets/img/FedCollab/overview.png
importance: 1
category: work
---

# Optimizing the Collaboration Structure in Cross-Silo Federated Learning

[Wenxuan Bao](https://baowenxuan.github.io/)<sup>1</sup>, &nbsp;
[Haohan Wang](https://haohanwang.github.io/)<sup>1</sup>, &nbsp;
[Jun Wu](https://publish.illinois.edu/junwu3/)<sup>1</sup>, &nbsp;
[Jingrui He](https://www.hejingrui.org/)<sup>1</sup>

<sup>1</sup>University of Illinois Urbana-Champaign

ICML 2023 &nbsp;
[\[arxiv\]](https://arxiv.org/abs/2306.06508) &nbsp;
[\[poster\]](https://github.com/baowenxuan/FedCollab/blob/master/material/FedCollab_poster.pdf) &nbsp;
[\[slides\]](https://github.com/baowenxuan/FedCollab/blob/master/material/FedCollab_slides.pdf) &nbsp;
\[talk\] &nbsp;
[\[code\]](https://github.com/baowenxuan/FedCollab) &nbsp;
[\[virtual site (registration required)\]](https://icml.cc/virtual/2023/poster/23569)

------

## Paper Summary

We propose FedCollab to alleviate the negative transfer problem in federated learning (FL) by clustering clients into non-overlapping coalitions based on their distribution distances and data quantities. 
- Theory: We analyze how clustered FL performance is affected by two key factors: distribution distance and data quantity.
- Algorithm: We propose FedCollab to solve for the best collaboration structure.
- Extensive experiments: We test FedCollab under label shift, feature shift and concept shift with various models / datasets. 

------

## Background

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/FedCollab/fls.png" title="learning scenarios" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison of different learning scenarios. 
</div>

In global FL, multiple clients collaborate to train a shared machine learning model without sharing their raw data. Although global FL can utilize more data samples, when clients have non-IID data, global FL suffers from the **negative transfer** problem, i.e., the global model can be even worse the local model. 

Clustered FL groups clients into coalitions based on distributions; each client only shares model with clients in the same coalition.

**Question**: *What is the optimal clustering structure*, i.e., which clients should train shared model?

------

## Theoretical Analysis



<!-- ## Introduction

We consider a FL system with $N$ clients $1, \cdots, N$ connected to a central server. 

## Method


## Result

We conduct 

## Acknowledgements -->

