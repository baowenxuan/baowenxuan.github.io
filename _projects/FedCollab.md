---
layout: page_wo_title
title: [ICML 2023] FedCollab
description: Optimizing the Collaboration Structure in Cross-Silo Federated Learning
img: assets/img/FedCollab/overview.png
importance: 1
category: work
---

# Optimizing the Collaboration Structure in Cross-Silo Federated Learning

[Wenxuan Bao](https://baowenxuan.github.io/), 
[Haohan Wang](https://haohanwang.github.io/), 
[Jun Wu](https://publish.illinois.edu/junwu3/), 
[Jingrui He](https://www.hejingrui.org/)

[[arxiv](https://arxiv.org/abs/2306.06508)] [poster] [slides] [talk] [code] [bibtex]

We propose FedCollab to alleviate the negative transfer problem in federated learning by clustering clients into non-overlapping coalitions based on their distribution distances and data quantities. 

- Theory: We analyze how clustered FL performance is affected by two key factors: distribution distance and data quantity.
- Algorithm: We propose FedCollab to solve for the best collaboration structure.
- Extensive experiments: We test FedCollab under label shift, feature shift and concept shift with various models / datasets. 

## Abstract

In federated learning (FL), multiple clients collaborate to train machine learning models together while keeping their data decentralized. Through utilizing more training data, FL suffers from the potential negative transfer problem: the global FL model may even perform worse than the models trained with local data only. In this paper, we propose FedCollab, a novel FL framework that alleviates negative transfer by clustering clients into non-overlapping coalitions based on their distribution distances and data quantities. As a result, each client only collaborates with the clients having similar data distributions, and tends to collaborate with more clients when it has less data. We evaluate our framework with a variety of datasets, models, and types of non-IIDness. Our results demonstrate that FedCollab effectively mitigates negative transfer across a wide range of FL algorithms and consistently outperforms other clustered FL algorithms.

## Introduction

We consider a FL system with $N$ clients $1, \cdots, N$ connected to a central server. 

## Method


## Result

We conduct 

## Acknowledgements

