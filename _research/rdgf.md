---
layout: research
title: 'Identifying Rare Disease Associated Transcriptional Programs'
caption: A network-based framework that integrates single-cell RNA-seq to identify tissue-specific transcriptional programs underlying rare diseases.
description: >
  Rare diseases affect millions worldwide, yet identifying their causal genes remains challenging. In this project, we developed RDGeneFinder, a scalable and interpretable gene-prioritization framework that extends GLOWgenes with topology-based network selection and transcriptomic re-ranking to improve rare disease gene discovery.
date: 2026-01-10
image: 
  path: /assets/img/research/rdgf.jpg
  srcset: 
    1920w: /assets/img/research/rdgf.jpg
    960w:  /assets/img/research/rdgf05.jpg
    480w:  /assets/img/research/rdgf025.jpg
accent_color: '#00539B'
accent_image:
  background: '#00539B'
theme_color: '#012169'
sitemap: false
---

Rare diseases collectively affect approximately 5% of the global population, and nearly 80% have a genetic basis, making accurate gene prioritization essential for diagnosis and therapeutic development. While published methods such as [GLOWgenes][glow] use multi-network random walks to rank candidate genes, they rely on exhaustive cross-validation across 33 biological networks and can dilute disease-relevant signal when biology is concentrated in only a few networks. To address these limitations, we developed RDGeneFinder, a scalable and interpretable extension of GLOWgenes for rare disease gene prioritization. PickNet, our network selection component, replaces 20-fold cross-validation with seed-gene degree and density scoring to efficiently identify the most disease-relevant network per knowledge category, reducing runtime by up to 4×. We further introduce a differential expression–guided re-ranking step that integrates scRNA-seq transcriptomic signals to refine the top of the candidate list, improving precision@10 by up to 100% in diseases such as cystic fibrosis and Prader-Willi syndrome.

[glow]:https://www.translationalbioinformaticslab.es/tblab-home-page/tools/glowgenes