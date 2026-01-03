---
layout: post
title: Gaussian Mixture Models
description: >
  Gaussian Mixture Models, updated at 11 Aug 2024
image: 
  path: assets/img/blog/gmm.png
  srcset:
    1060w: /assets/img/blog/gmm.png
    530w:  /assets/img/blog/gmm_50.png
    265w:  /assets/img/blog/gmm_25.png
sitemap: false
hide_last_modified: true
---

# Gaussian Mixture Models

* toc
{:toc .large-only}

## What is Gaussian Mixture Models (GMM)?

A Gaussian Mixture Models (GMM or Mixture of Gaussians) is a probabilitsitc model used to represent a mixture of multiple Gaussian distributions. 

## Motivation
K-means algorithm would typically assign each data to exactly one cluster, but what if these clusters are overlapping. In this case, we do not have enough information to tell which cluster are right or which cluster are dominating. In Gaussian mixture models, clusters are modeled as gaussian components which has its own mean and variance. In this case, we could assign each data to cluster with some probability. This approache gives probability model of data ("generative").

## Concepts of GMM
Suppose we have $$ N $$ data samples, thus $$ x_i $$ is $$ i $$th data and $$ j $$ means the Gaussian component $$ j $$
#### Responsibility ($$\gamma_{ij}$$)

$$
\gamma_{ij} = \frac{\pi_i \mathcal{N}(x_j \mid \mu_i, \Sigma_i)}{\sum_{k=1}^K \pi_k \mathcal{N}(x_j \mid \mu_k, \Sigma_k)}
$$

#### Mean ($$ \mu_i $$)

The mean vector for each Gaussian component $$ i $$, representing the center of the Gaussian distribution.

$$
\mu_i = \frac{\sum_{j=1}^N \gamma_{ij} x_j}{\sum_{j=1}^N \gamma_{ij}}
$$


#### Covariances ($$ \Sigma_i $$)
The covariance matrix for each Gaussian component, representing the spread and orientation of the Gaussian distribution in the feature space.

$$
\Sigma_i = \frac{\sum_{j=1}^N \gamma_{ij} (x_j - \mu_i)(x_j - \mu_i)^T}{\sum_{j=1}^N \gamma_{ij}}
$$


#### Weights ($$ \pi_i $$)

The mixing coefficients representing the weight of each Gaussian component in the mixture.

$$
\pi_i = \frac{\sum_{j=1}^N \gamma_{ij}}{N}
$$

## Fitting a GMM

### Initialization

### Expectation-Maximization (EM) Algorithm
We use Expectation-Maximization (EM) algorithm to iteratively improve the model fit. It is used to optimize different unsupervised machine learning algorithms and it consists 2 steps which are E-Step and M-Step.

#### Expectation Step (E-Step)
Calculate the probability that each data point belongs to each Gaussian component. We use the current estimates of the means, covariance, and weights. In this step, we will re-caculate the responsibilities $$ \gamma_{ij}$$ for each data point $$ x_j $$ and each Gaussian component $$ i $$.


#### Maximization Step (M-Step)
Update the parameters of the Gaussian components (means, covariances, and weights) to maximize the likelihood of the data given the current probabilities. In this step, we will update $$ \mu_i $$, $$ \Sigma_i $$, as well as $$ \pi_i $$ for Gaussian component $$ i $$. Thus, we need to
- For each Gaussian component $$ i $$, compute the sum of the responsibilities $$ \gamma_{ij} $$ over all $$ N $$ data points.
- Update Mean $$ \mu_i $$, $$ \Sigma_i $$, as well as $$ \pi_i $$ using the definitions above.

#### Covergence:
The algorithm iterates betwee nthe E-Step and M-Step until convergence, which is typically when chagnes in the log-likelihood or parameters are below a certain threshold. Each step increases the log-likelihood of our model.