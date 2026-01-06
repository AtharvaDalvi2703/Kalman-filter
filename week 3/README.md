
---

## Task 1: Q-Learning Parameter Selection (FrozenLake)

The first task only required submitting the **parameter values** used in the provided Q-learning skeleton for the FrozenLake environment.  
No code modifications were required beyond setting these values.

### Parameters Used

```python
alpha = 0.07        # Learning rate
gamma = 0.99        # Discount factor

epsilon = 1.0       # Initial exploration rate
epsilon_min = 0.01  # Minimum exploration rate
epsilon_decay = 0.995


# Mountain Climbing using Deep Q-Learning

This notebook explores reinforcement learning in environments with **continuous state spaces and delayed rewards** using the MountainCar problem.  
The goal is to understand why tabular Q-learning fails in such settings and how **Deep Q-Learning (DQN)** overcomes these limitations through function approximation.

---

## Environment Description

The MountainCar environment consists of a car located in a valley between two hills.  
The engine is not powerful enough to directly climb the right hill, so the agent must first move **away from the goal** to build momentum.

Key properties:
- **State space:** Continuous (position, velocity)
- **Action space:** Discrete (push left, no push, push right)
- **Reward:** −1 at each timestep until the goal is reached
- **Challenge:** Long-term planning with delayed rewards

---

## Why Tabular Q-Learning Fails Here

Initial attempts using tabular Q-learning (via state discretization) reveal several issues:
- Performance is extremely sensitive to discretization resolution
- Increasing bins leads to high memory and computation costs
- Learning remains unstable and inconsistent

These limitations motivate the use of **Deep Q-Networks**, which generalize across states instead of memorizing them.

---

## Approach Used in This Notebook

### 1. Deep Q-Network (DQN)
- A neural network is used to approximate the action-value function \( Q(s, a) \)
- This allows learning directly from continuous states without explicit discretization

### 2. Experience Replay
- Transitions are stored in a replay buffer
- Random sampling breaks temporal correlations and stabilizes training

### 3. Target Network
- A separate target network is used for computing TD targets
- Helps reduce oscillations and feedback loops during learning

### 4. Exploration Strategy
- ε-greedy exploration with slow decay
- Exploration is maintained for a longer duration due to delayed rewards

---

## Training Behavior & Observations

- Early episodes show random and inefficient behavior
- Over time, the agent learns to:
  - Move left initially to gain momentum
  - Use velocity effectively to reach the goal
- Episode lengths gradually decrease, indicating learning progress

Perfect convergence is not expected, but the learned policy shows **qualitatively sensible behavior** and clear improvement over tabular methods.

---

## Files Included

- `mountain_climbing.ipynb` — Full implementation of Deep Q-Learning for MountainCar


