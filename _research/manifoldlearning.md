---
layout: research
title: 'Manifold Learning Example'
caption: Manifold Learning Examples and their experiments
description: >
  Manifold Learning algorithms, Non-linear dimension reduction
date: 7 Jan 2023
image: 
  path: /assets/img/research/manifold.png
  srcset: 
    1920w: /assets/img/research/manifold.jpg
    960w:  /assets/img/research/manifold05.jpg
    480w:  /assets/img/research/manifold025.jpg
links:
  - title: Link
    url: https://tce.cs.washington.edu/
accent_color: '#4fb1ba'
accent_image:
  background: '#193747'
theme_color: '#193747'
sitemap: false
---

Manifold Learning (ML) algorithms -- also called Embedding algorithms -- can help us interpret data with many dimensions (such as a cloud of word embeddings or of configurations of a molecule) by mapping it to 2D or to 3D where we can see it. But is what we are seeing the real shape of the data? Almost always, ML algorithms distort the shape. Sometimes the distortions are unimportant, but sometimes they can make us see clusters, "arms", holes, and "horseshoes" (what we will call artefacts) that are not properties of the data, but just effects of the algorithm and parameter choices.

This project illustrates some of the most common effects and artefacts you will encounter, as you start using Embedding algorithms for your real data. The artefacts are not symptoms of "too little data" -- most of them persist even when the data size n goes to infinity! We chose simple artificial examples as the most common effects are present even with the simplest data.

The good news is that once you are aware of their presence, the artefacts and distorions can be recognized and methods exist to circumvent or to correct them.
