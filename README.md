# Snake Machine Learning RL Model

A deep reinforcement learning project in which an agent learns to play the classic Snake game from scratch — no hard-coded movement rules, no predefined strategies.

Using Deep Q-Learning (DQN), the agent observes the game state, predicts optimal actions, and refines its survival strategy through experience replay and epsilon-greedy exploration.

---

## Repository Structure

```
snake-ml-rl/
├── agent.py
├── model.py
├── game.py
└── helper.py
```

---

## Modules

### agent.py — RL Agent

Implements the core training loop. The agent observes the current game state, selects actions via epsilon-greedy exploration, stores transitions in a replay buffer, and updates the network using sampled mini-batches.

**Key concepts:** Deep Q-Learning, epsilon-greedy exploration, experience replay, short- and long-term memory updates.

---

### model.py — Deep Q-Network

A fully connected neural network that maps game state observations to Q-values over the action space (straight, turn left, turn right). Includes the training step with mean-squared-error loss and an Adam optimizer.

**Key concepts:** Q-value approximation, Bellman equation, neural network training with PyTorch.

---

### game.py — Snake Environment

A customizable Snake environment built with Pygame. Handles game logic, collision detection, food placement, and score tracking. Exposes a clean step interface for the agent to interact with each frame.

**Key concepts:** Custom environment design, frame-by-frame agent interaction, reward shaping.

---

### helper.py — Training Visualizer

Plots live training progress — score per episode and mean score over time — so training dynamics are visible without needing TensorBoard.

**Key concepts:** Live matplotlib plotting, training diagnostics.

---

## Training System

**Algorithm:** Deep Q-Learning (DQN)

**State representation:** 11-dimensional boolean vector encoding danger ahead/left/right, current direction, and food location relative to the snake's head

**Action space:** 3 actions — go straight, turn left, turn right

**Exploration:** Epsilon-greedy with decay over episodes — early episodes explore widely, later episodes exploit learned Q-values

**Experience replay:** Transitions stored in a memory buffer and sampled randomly to break temporal correlations during training

The best-performing model is saved automatically throughout training.

---

## Stack

| Area | Libraries |
|---|---|
| Environment | Pygame |
| Neural Network | PyTorch |
| Visualization | Matplotlib |
| Core | Python 3.x standard library |

---

## How to Run

**Requirements:** Python 3.x, PyTorch, Pygame, Matplotlib

**Install dependencies:**
```bash
pip install torch pygame matplotlib
```

**Train the agent:**
```bash
python agent.py
```

**Watch a trained model play:**
```bash
python game.py
```

---
