# Deep Q-Network and Rainbow Extensions on MinAtar  
**Author:** Anushka Khatri  
**Reinforcement Learning Lab – University of Freiburg**

---

## Overview

This repository contains the implementation and experiments for the lab project titled:  
**"Deep Q-Network and Rainbow Extensions on MinAtar."**

The project explores improvements to Deep Q-Networks (DQN) through Rainbow extensions—including Double DQN, Dueling Networks, Noisy Nets, Multi-step Learning, and Distributional RL—using the Breakout environment from MinAtar.

---

## Repository Structure
.
├── agent.py # DQN agent with modular extension support
├── dqn.py # DQN architecture (supports noisy/distributional)
├── dual_networks.py # Dueling DQN architecture and update
├── multi_step_learning.py # Multi-step replay buffer logic
├── noisy_linear.py # NoisyNet layer implementation
├── replay_buffer.py # Standard experience replay
├── train.py # Training and evaluation script
├── sweep_config.yaml # W&B sweep configuration
├── utils.py # Training utilities and logging
└── README.md


---

## Extensions Implemented

| Extension        | Description                                                              |
| ---------------- | ------------------------------------------------------------------------ |
| `Double DQN`     | Reduces Q-value overestimation by decoupling action selection/evaluation |
| `Dueling DQN`    | Separates state-value and action-advantage streams                       |
| `Noisy Nets`     | Adds parameter noise for exploration instead of ε-greedy                 |
| `Multi-step`     | Uses n-step rewards for better credit assignment                         |
| `Distributional` | Learns return distribution via Categorical DQN (C51)                     |

---
## Evaluation Protocol

Episodes: 1000

Update Frequency: every 100 steps

Replay Buffer Size: 100,000

Metric: Average reward over episodes

Output: wandb logs, reward plots, animated rollouts

---

## Results Summary

Best config: Double DQN + Dueling + Noisy Nets

Achieved ~70% improvement in average reward compared to vanilla DQN

Noisy Nets enabled more efficient exploration

Multi-step learning (n = 3) improved convergence

---

## Author

Anushka Khatri
Master's Student, University of Freiburg
Supervised by: RL Lab Instructors
Course: Reinforcement Learning Lab (Winter 2024/25)

---

## Acknowledgements
Thanks to the Reinforcement Learning Lab at the University of Freiburg for guidance and computational resources.
Collaborators: Bhagyashree Rane, Deniz Çelebi
