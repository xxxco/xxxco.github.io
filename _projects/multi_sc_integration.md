---
layout: project
title: 'Multimodal Single-Cell Integration for Protein Prediction from RNA'
caption: Multimodal Single-Cell Integration for Protein Prediction from RNA
description: >
  This project investigates multimodal single-cell integration by predicting protein expression levels from RNA sequencing data using machine learning models. Linear regression, gradient boosting, and neural networks are evaluated to understand predictive performance and feature importance in CITE-seq data.
date: 30 May 2023
image: 
  path: /assets/img/research/tce.jpg
  srcset: 
    1920w: /assets/img/research/tce.jpg
    960w:  /assets/img/research/tce05.jpg
    480w:  /assets/img/research/tce025.jpg
# links:
#   - title: Link
#     url: https://github.com/chunqcao0822/CSE529_FinalProject/tree/main
accent_color: '#4fb1ba'
accent_image:
  background: '#193747'
theme_color: '#4B2D83'
sitemap: false
---

In this study, we explore the relationship between RNA expression and protein abundance at the single-cell level using CITE-seq data from the Kaggle Multimodal Single-Cell Integration challenge. After preprocessing over 70,000 cells and filtering features to preserve gene–protein correspondence, we applied dimensionality reduction via truncated SVD and visualized cell-type structure using PCA and UMAP. We trained and compared multiple predictive models, including linear regression, LightGBM, and a multilayer perceptron, to predict 140 protein targets. Model performance was evaluated using Pearson correlation and mean squared error, with LightGBM achieving the strongest results. To interpret model behavior, we employed SHAP analysis to examine feature importance and test the hypothesis that gene expression corresponding to a target protein would act as a dominant predictor. While the models achieved strong predictive accuracy, feature attribution results suggested that dimension-reduced components and broader expression patterns, rather than single matching genes, drove protein prediction.

**Skills & Tools**: Single-Cell RNA-seq · Multimodal Data Integration · Machine Learning · LightGBM · Linear Regression · Neural Networks · SHAP · Scanpy · Dimensionality Reduction · Python

**Impact**: Demonstrates a practical machine learning pipeline for multimodal single-cell data integration and highlights the challenges of interpreting feature contributions in high-dimensional biological systems.


<!-- ```yml
google_fonts: false
font:         false
font_heading: false
font_code:    false
``` -->
<!-- 
The configuration I use to enable the system font on my site. Feel free to copy!
{:.figcaption} -->
