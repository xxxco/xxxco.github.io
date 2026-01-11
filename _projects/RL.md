---
layout: project
title: 'Reinforcement Learning Algorithm Benchmarking'
caption: Benchmarks DQN, A2C, and PPO through component-level ablations, revealing how distinct stabilization mechanisms drive learning stability, with PPO showing the most robust performance.
description: >
  This project systematically analyzes the role of key stabilization components in deep reinforcement learning by performing controlled ablations of DQN, A2C, and PPO on the LunarLander-v3 environment. The study shows that different algorithm families rely on distinct mechanisms for stability, with PPO achieving the most robust performance.
date: 12 Dec 2025
image: 
  path: /assets/img/project/rl.jpg
  srcset: 
    1920w: /assets/img/project/rl.jpg
    960w:  /assets/img/project/rl05.jpg
    480w:  /assets/img/project/rl025.jpg
# links:
#   - title: Link
#     url: https://github.com/williamconvertino/sae-toxicity-supression
accent_color: '#00539B'
accent_image:
  background: '#00539B'
theme_color: '#012169'
sitemap: false
---

In this study, we conduct a component-level ablation analysis to understand why certain deep reinforcement learning algorithms are more stable and effective than others. Using the LunarLander-v3 benchmark, we first compare baseline performance of DQN, A2C, and PPO, and then selectively remove or modify their core stabilization mechanisms, including replay buffers and target networks in DQN, generalized advantage estimation (GAE) in A2C, and clipped policy updates in PPO. The results reveal that algorithmic stability depends strongly on these components but in different ways across methods: DQN becomes unstable without replay or target networks, A2C suffers from high variance without GAE, and PPO fails catastrophically when the clipping mechanism is removed. Overall, PPO demonstrates superior stability and learning efficiency, helping explain the dominance of policy optimization methods in modern continuous control tasks.


**Skills & Tools**: Reinforcement Learning · DQN · A2C · PPO · Algorithmic Ablation · Policy Optimization · OpenAI Gymnasium · Experimental Evaluation

**Impact**: Provides empirical insight into which algorithmic components are essential for stability in deep reinforcement learning, informing both model selection and the design of more robust RL systems.


<!-- ```yml
google_fonts: false
font:         false
font_heading: false
font_code:    false
``` -->
<!-- 
The configuration I use to enable the system font on my site. Feel free to copy!
{:.figcaption} -->
