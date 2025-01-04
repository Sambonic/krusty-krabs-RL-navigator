# Krusty Krabs Navigator

The customers dropped their money and went on a rampage to find who stole it. This is the theme of this project where we designed an intelligent robot agent inspired by Mr. Krabs from SpongeBob SquarePants that collects money dropped by customers at the Krusty Krab restaurant. Mr.Krabs and his robot clone need to gather the money quickly before the angry customers find him. To achieve this, our agents map their environments, implement key AI path-planning algorithms, and account for dynamic rerouting, obstacle avoidance, and multi-agent coordination. 

#### Last Updated: December 23rd, 2024
## Table of Contents

1. [Installation](#installation)
2. [Objectives](#objectives)
3. [Environment Design](#environment-design)
4. [Key Features](#key-features)
5. [Implementation Details](#implementation-details)
6. [Challenges and Solutions](#challenges-and-solutions)
7. [Testing and Results](#testing-and-results)

<a name="installation"></a>
## Installation

Make sure you have [Python](https://www.python.org/downloads/) installed.

Follow these steps to set up the environment and run the application:

1. Clone the Repository:
   ```bash
   git clone https://github.com/Sambonic/krusty-krabs-navigator
   ```
   ```bash
   cd krusty-krabs-navigator
   ```

2. Create a Python Virtual Environment:
```bash
python -m venv env
```

3. Activate the Virtual Environment:
- On Windows:
  ```
  env\Scripts\activate
  ```

- On macOS and Linux:
  ```
  source env/bin/activate
  ```
4. Ensure Pip is Up-to-Date:
  ```
  python.exe -m pip install --upgrade pip
  ```
5. Install Dependencies:

   ```bash
   pip install .
   ```
Or simply run the pip install line in the notebook

<a name="objectives"></a>
## Objectives

- Implement a DDQN algorithm to train the agent to navigate the environment efficiently.
- Develop a reward system that incentivizes the agent to reach the target quickly while avoiding obstacles.
- Create a lore-accurate environment based on the Krusty Krabs restaurant for simulation purposes.

<a name="environment-design"></a>
## Environment Design

- The environment and assets were designed using **Ibis Paint X** to resemble the Krusty Krabs restaurant.
- Static and dynamic obstacles, including customers, were added to create realistic challenges for the agent.


<a name="key-features"></a>
## Key Features

### Reinforcement Learning Algorithm
- Utilized **Double Deep Q-Network (DDQN)** for stability and to avoid Q-value overestimation.
- Employed a target and policy network with periodic updates for stable training.

### Neural Network Architecture
- A feedforward neural network with three hidden layers of 64 neurons each, using ReLU activation.

### Hyperparameter Tuning
- **Target Network Update Frequency:** Every 100 episodes.
- **Replay Memory Size:** 100,000.
- **Batch Size:** 32.
- **Learning Rate:** 0.0001.
- **Exploration Strategy:** Epsilon-greedy approach (decay from 1.0 to 0.01 with a rate of 0.998).

### Reward and Penalty System
- **Reward:** Distance-based and success-based incentives (e.g., reaching the target yields a reward of 50.0).
- **Penalty:** Distance and time-based penalties, with a harsh penalty (-5.0) for invalid moves.

---

<a name="implementation-details"></a>
## Implementation Details

### Technologies Used
- Python with PyGame for simulation
- NumPy for occupancy grid management
- Priority Queues for pathfinding algorithms
- Custom asset design with Ibis Paint X

### Key Components
- DDQN class for agent behavior
- Environment class to house reward-penalty logic

<a name="challenges-and-solutions"></a>
## Challenges and Solutions

- **Complex Environment:** Improved exploration strategy and reward system.
- **Unstable Convergence:** Enhanced neural network architecture with additional layers.
- **Overfitting:** Adopted DDQN to leverage its mechanisms for stability.

<a name="testing-and-results"></a>
## Testing and Results

- **Comparison of Algorithms:**

| Algorithm | Time Elapsed (s) |
|-----------|-------------------|
| A*        | 5.47             |
| Dijkstra  | 5.54             |
| DDQN      | 5.37             |

- The DDQN agent demonstrated slightly better performance in efficiency compared to traditional search algorithms.

---
