# Flappy Bird Reinforcement Learning

A Reinforcement Learning project built with Python, Gymnasium, and `flappy-bird-gymnasium`.

The goal of this project is to experiment with Reinforcement Learning by training an agent to play Flappy Bird using observations from the game environment and progressively improving its decision-making strategy.

## Project Structure

```text
FlappyBird-RL/
│
├── .venv/                  # Python virtual environment
│
├── src/                    # Source code
│   └── flappy_bird_random.py
│
├── notebooks/              # Experiments and analysis
│
├── models/                 # Saved trained models
│
├── requirements.txt        # Project dependencies
│
├── .gitignore
└── README.md
```

## Tech Stack

- Python
- Gymnasium
- Flappy Bird Gymnasium
- Pygame
- NumPy
- Matplotlib

## Environment

This project uses the `FlappyBird-v0` environment provided by `flappy-bird-gymnasium`.

The environment provides:

- Game observations
- Action space
- Rewards
- Episode termination
- Game rendering
- Optional LIDAR-based observations

Example environment setup:

```python
import flappy_bird_gymnasium
import gymnasium

env = gymnasium.make(
    "FlappyBird-v0",
    render_mode="human",
    use_lidar=True
)
```

## Current Stage

The project currently starts with a **random agent**.

The agent selects actions randomly using:

```python
action = env.action_space.sample()
```

This stage is mainly used to verify that the environment, observations, actions, rewards, and rendering are working correctly.

## Running the Project

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd FlappyBird-RL
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the virtual environment

Windows CMD:

```cmd
.venv\Scripts\activate
```

### 4. Install dependencies

```cmd
pip install -r requirements.txt
```

If `requirements.txt` has not been created yet:

```cmd
pip install flappy-bird-gymnasium gymnasium pygame numpy matplotlib
```

Then save the dependencies:

```cmd
pip freeze > requirements.txt
```

### 5. Run the random agent

```cmd
python src\flappy_bird_random.py
```

A Flappy Bird game window should open and the bird will perform random actions.

## Basic Environment Loop

The core RL interaction follows this cycle:

```text
        ┌──────────────┐
        │ Reset Env    │
        └──────┬───────┘
               ↓
        ┌──────────────┐
        │ Observation  │
        └──────┬───────┘
               ↓
        ┌──────────────┐
        │ Choose Action│
        └──────┬───────┘
               ↓
        ┌──────────────┐
        │ Environment  │
        │    Step      │
        └──────┬───────┘
               ↓
       ┌────────┴────────┐
       ↓                 ↓
    Reward          Next State
       │                 │
       └────────┬────────┘
                ↓
          Episode Done?
           /        \
         No          Yes
         │            │
         └──→ Repeat  └──→ Reset
```

## Learning Objective

The long-term objective is to train an agent that learns:

```text
Observation
     ↓
State representation
     ↓
Action selection
     ↓
Flap / Don't Flap
     ↓
Reward
     ↓
Update policy
     ↓
Improved decisions
```

Instead of manually controlling the bird, the agent should learn a policy that maximizes its cumulative reward.

## Future Experiments

Some experiments planned for this project:

- Different state representations
- Different reward functions
- Epsilon decay strategies
- Learning-rate experiments
- Discount-factor experiments
- Q-learning vs DQN
- Different neural network architectures
- Training stability
- Episode reward visualization

## Requirements

The main dependencies are:

```text
flappy-bird-gymnasium
gymnasium
pygame
numpy
matplotlib
```

The exact versions used for the project are stored in:

```text
requirements.txt
```

## Learning Purpose

This project is part of my Reinforcement Learning learning journey.

The focus is not only on making the agent play the game, but also on understanding the fundamental concepts behind Reinforcement Learning:

- Environment
- State
- Action
- Reward
- Policy
- Value Function
- Q-Table
- Exploration vs Exploitation
- Q-Learning
- Deep Q-Networks
- Experience Replay
- Target Networks

## Author

**Binay Panda**

Computer Science Engineering Student

GitHub: [Binay-panda19](https://github.com/Binay-panda19)
