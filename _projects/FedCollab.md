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

We consider an FL system with $$N$$ clients, each client $$i$$ has $$m_i$$ samples $$\hat{\mathcal{D}}_i = \{(\boldsymbol{x}_k^{(i)}, \boldsymbol{y}_k^{(i)})\}_{k=1}^{m_i}$$ i.i.d. drawn from its local distribution $$\mathcal{D}_i$$. $$h$$ is the ML model and $$\ell$$ is the risk function. Denote the quantity distribution $$\boldsymbol{\beta} = [\beta_1, \cdots, \beta_N] = [\frac{m_1}{m}, \cdots, \frac{m_N}{m}]$$ where $$m = \sum_{i=1}^N m_i$$. 
- Client $$i$$'s *local empirical risk*: $$\hat{\epsilon}_i(h) = \frac{1}{m_i}\sum_{k=1}^{m_i} \ell(h(\boldsymbol{x}_k^{(i)}), \boldsymbol{y}_k^{(i)})$$
- Client $$i$$'s *local expected risk*: $$\epsilon_i(h) = \mathbb{E}_{(\boldsymbol{x}, \boldsymbol{y}) \in \mathcal{D}_i} \ell(h(\boldsymbol{x}), \boldsymbol{y})$$

**Theorem 3.3.** (informal) Let $$\hat{h}_{\boldsymbol{\alpha}_i} = \argmin_{h \in \mathcal{H}} \sum_{j=1}^N \alpha_{ij} \hat{\epsilon}_j(h)$$ where $$\sum_{j=1}^N \alpha_{ij} = 1$$. With probability at least $$1 - 2\delta$$, 

$$
\epsilon_i(\hat{h}_{\boldsymbol{\alpha}_i}) \leq 
        \underbrace{\vphantom{\frac ab}\epsilon_i( h_i^* )}_{\text{irreducible error}} + \ 
        2 \underbrace{\vphantom{\frac ab}\phi_{|\mathcal{H}|}(\boldsymbol{\alpha}_i, \boldsymbol{\beta}, m, \delta)}_{\text{quantity-aware function}} + \ 
        2 \sum_{j \neq i} \alpha_{ij} \underbrace{\vphantom{\frac ab}D(\mathcal{D}_i, \mathcal{D}_j)}_{\text{distribution distance}}
$$
where 
- the quantity-aware function $$\phi_{|\mathcal{H}|}(\boldsymbol{\alpha}_i, \boldsymbol{\beta}, m, \delta) = \sqrt{\left( \sum_{j=1}^N \frac{\alpha_{ij}^2}{\beta_j} \right) \left( \frac{2d \log (2m + 2) + \log(4 / \delta)}{m} \right)}$$, and
- the distribution distance $$D(\mathcal{D}_i, \mathcal{D}_j) = \max_{h \in \mathcal{H}} \left| \epsilon_i(h) - \epsilon_j(h) \right|$$. 

<!-- ## Introduction

We consider a FL system with $$N$$ clients $$1, \cdots, N$$ connected to a central server. 

## Method


## Result

We conduct 

## Acknowledgements -->

