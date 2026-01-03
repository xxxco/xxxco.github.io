---
layout: research
title: 'Spatial Speech Translation'
caption: Spatial speech translation is an intelligent hearable system that translates speakers in the wearer’s auditory space, preserving the direction and unique voice characteristics of each speaker in the binaural output.
description: >
  "Spatial speech translation" is an intelligent hearable system that translates speakers in the wearer’s auditory space, preserving the direction and unique voice characteristics of each speaker in the binaural output.
date: 26 April 2025
image: 
  path: /assets/img/research/spatialst.png
  srcset: 
    1920w: /assets/img/research/spatialst.png
    960w:  /assets/img/research/spatialst.png
    480w:  /assets/img/research/spatialst.png
links:
  - title: Link
    url: https://tce.cs.washington.edu/
accent_color: '#4fb1ba'
accent_image:
  background: '#193747'
theme_color: '#193747'
sitemap: false
---

Imagine being in a crowded space where people speak a different language and having hearables that transform the auditory space into your native language, while preserving the spatial cues for all speakers. We introduce spatial speech translation, a novel concept for hearables that translate speakers in the wearer’s environment, while maintaining the direction and unique voice characteristics of each speaker in the binaural output. To achieve this, we tackle several technical challenges spanning blind source separation, localization, real-time expressive translation, and binaural rendering to preserve the speaker directions in the translated audio, while achieving real-time inference on the Apple M2 silicon. Our proofof-concept evaluation with a prototype binaural headset shows that, unlike existing models, which fail in the presence of interference, we achieve a BLEU score of upto 22.01 when translating between languages, despite strong interference from other speakers in the environment. User studies further confirm the system’s effectiveness in spatially rendering the translated speech in previously