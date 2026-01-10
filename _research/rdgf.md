---
layout: research
title: 'Identifying Rare Disease Associated Transcriptional Programs'
caption: A network-based framework that integrates single-cell RNA-seq to identify tissue-specific transcriptional programs underlying rare diseases.
description: >
  Rare diseases affect millions worldwide, yet identifying their causal genes remains challenging. In this project, we developed Rare Disease Gene Finder (RDGF), a scalable and interpretable gene-prioritization framework that integrates single-cell RNA-seq to improve rare disease diagnosis and discovery.
date: 2026-01-10
image: 
  path: /assets/img/research/rdgf.jpg
  srcset: 
    1920w: /assets/img/research/rdgf.jpg
    960w:  /assets/img/research/rdgf05.jpg
    480w:  /assets/img/research/rdgf025.jpg
# links:
#    - title: Link
#      url: https://www.ece.uw.edu/wp-content/uploads/2024/04/Research-Showcase-2024-Poster-Jason-Isa.pdf
accent_color: '#4fb1ba'
accent_image:
  background: '#193747'
theme_color: '#012169'
sitemap: false
---

Rare diseases collectively affect approximately 5% of the global population, and nearly 80% have a genetic basis, making accurate gene prioritization essential for diagnosis and therapeutic development. While published methods such as [GLOWgenes][glow] use multi-network random walks to rank candidate genes, they rely on population- or tissue-aggregated data and can lose accuracy when only a small number of disease genes are known. To address these limitations, we developed Rare Disease Gene Finder (RDGF), a scalable and interpretable network-based framework for rare disease gene prioritization. By integrating single-cell RNA sequencing–derived coexpression patterns, RDGF captures tissue-specific biological signals that are missed by aggregated approaches, enabling more accurate and biologically meaningful gene discovery.

[glow]:https://www.translationalbioinformaticslab.es/tblab-home-page/tools/glowgenes
