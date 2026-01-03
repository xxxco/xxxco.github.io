---
layout: research
title: 'Effect of Adaptation Rate and Cost Display in a Human-AI Interaction Game'
caption: Effect of Adaptation Rate and Cost Display in a Human-AI Interaction Game
description: >
  Without changing the AI agent’s adaptive algorithm, can we influence the Human-AI
  game outcome by changing the Human’s feedback information and model these behavior
  changes within a game theoretic model?
date: 7 Apr 2024
image: 
  path: /assets/img/research/effectofadapation.jpg
  srcset: 
    1920w: /assets/img/research/effectofadapation.jpg
    960w:  /assets/img/research/effectofadapation05.jpg
    480w:  /assets/img/research/effectofadapation02.jpg
links:
  - title: Link
    url: https://www.ece.uw.edu/wp-content/uploads/2024/04/Research-Showcase-2024-Poster-Jason-Isa.pdf
accent_color: '#4fb1ba'
accent_image:
  background: '#193747'
theme_color: '#193747'
sitemap: false
---

As interactions between humans and AI become more prevalent, it is critical to have better predictors of human behavior in these interactions. We investigated how changes in the AI’s adaptive algorithm impact behavior predictions in two-player continuous games. In our experiments, the AI adapted its actions using a gradient descent algorithm under different adaptation rates while human participants were provided cost feedback. The cost feedback was provided by one of two types of visual displays: (a) cost at the current joint action vector, or (b) cost in a local neighborhood of the current joint action vector. Our results demonstrate that AI adaptation rate can significantly affect human behavior, having the ability to shift the outcome between two game theoretic equilibrium. We observed that slow adaptation rates shift the outcome towards the Nash equilibrium, while fast rates shift the outcome towards the human-led Stackelberg equilibrium. The addition of localized cost information had the effect of shifting outcomes towards Nash, compared to the outcomes from cost information at only the current joint action vector. Future work will investigate other effects that influence the convergence of gradient descent games.