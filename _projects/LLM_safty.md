---
layout: project
title: 'LLM Safety & Interpretability with Sparse Autoencoders'
caption: Uses sparse autoencoders to uncover interpretable features in large language models, enabling accurate detection and direct steering of toxic and hallucinatory behaviors.
description: >
  This project uses sparse autoencoders to identify interpretable internal features in large language models that are strongly associated with toxic and hallucinatory behaviors. We show that a small number of SAE features enable accurate safety detection and can be used to directly steer model behavior toward safer outputs.
date: 5 Dec 2025
image: 
  path: /assets/img/project/llm.jpg
  srcset: 
    1920w: /assets/img/project/llm.jpg
    960w:  /assets/img/project/llm05.jpg
    480w:  /assets/img/project/llm025.jpg
links:
  - title: Link
    url: https://github.com/williamconvertino/sae-toxicity-supression
accent_color: '#4fb1ba'
accent_image:
  background: '#193747'
theme_color: '#012169'
sitemap: false
---

Large language models often produce toxic or hallucinatory content, yet the internal representations driving these failures are difficult to interpret or control. In this project, we apply a pretrained sparse autoencoder to the Gemma-2B model to decompose hidden activations into sparse, human-interpretable features and study their relationship to safety behaviors. By comparing class-wise feature activations across NQOpen, ParaDetox, and RealToxicityPrompts datasets, we identify specific feature directions that reliably distinguish harmful from safe text. Linear classifiers trained on as few as ten top-ranked features achieve strong toxicity detection performance (AUROC up to 0.96), indicating that safety-relevant information is linearly separable in the SAE feature space. Beyond detection, we demonstrate causal utility through feature-level steering: suppressing toxicity-aligned features reduces toxic generation, while steering against hallucination-aligned features improves factual accuracy. Qualitative analyses of high-activation tokens confirm semantic coherence, with toxicity-aligned features corresponding to profane or hostile language. Overall, this work shows that sparse autoencoder features provide both interpretability and actionable control over safety-critical behaviors in large language models.


**Skills & Tools**: LLM Interpretability · Sparse Autoencoders · Transformer Models · PyTorch · Safety Evaluation

**Impact**: Enables interpretable detection and direct steering of toxic and hallucinatory behaviors in large language models.



<!-- ```yml
google_fonts: false
font:         false
font_heading: false
font_code:    false
``` -->
<!-- 
The configuration I use to enable the system font on my site. Feel free to copy!
{:.figcaption} -->
