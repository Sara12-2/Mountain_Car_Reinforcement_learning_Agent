# 🚗 Mountain Car Agent (Q-Learning with Gymnasium)

This project implements a **Q-learning agent** with epsilon-greedy exploration to solve the **MountainCar-v0** environment from [OpenAI Gymnasium](https://gymnasium.farama.org/).  

The agent learns to drive a car up the mountain using a **discretized state space** and Q-table updates.

---

## 🚀 Features
- Environment: **MountainCar-v0**
- **Q-learning** with epsilon-greedy policy
- **State discretization** for continuous observations
- **Q-table** update rule
- **Training reward tracking** and **performance plotting**
- Supports **real-time environment rendering**

---

## 📂 Requirements
Install dependencies before running:
```bash
pip install gymnasium numpy matplotlib
```
For rendering support:
```bash
pip install gymnasium[classic-control]
```
## 📜 How It Works

### 1.Discretization:
Continuous states (car position, car velocity) are mapped into discrete bins.

### 2.Q-Table:
The Q-table stores values for every (state, action) pair:
```bash
Q[position, velocity, action]
```
### 3.Epsilon-Greedy Policy:

With probability epsilon, take a random action (explore).

Otherwise, take the best known action (exploit).

### 4.Q-Update Rule:
``` bash
Q[s,a] = Q[s,a] + α * (r + γ * max(Q[s’,:]) - Q[s,a])
```
### 5.Training:
Over multiple episodes, the car learns to build momentum and reach the goal flag.
## ⚙️ Hyperparameters

The main hyperparameters in the script:
```bash
alpha = 0.1        # Learning rate
gamma = 0.99       # Discount factor
epsilon = 1.0      # Initial exploration rate
epsilon_decay = 0.995
epsilon_min = 0.01
episodes = 5000    # Training episodes
max_steps = 200    # Max steps per episode
n_states = 40      # Discretization bins
```
## 📊 Training Performance

At the end of training, the script plots the reward per episode:

X-axis → Episodes

Y-axis → Reward (higher is better, max = -110 average over 100 episodes)

Example output:
``` bash
Episode 1/5000   - Reward: -200
Episode 50/5000  - Reward: -200
Episode 5000/5000 - Reward: -120
```




