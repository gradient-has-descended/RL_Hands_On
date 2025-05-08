# Introduction to Reinforcement Learning

Given an agent, an environment, a set of actions, and the associated reward the agent can earn for each action, reinforcement learning allows us to learn a **policy**—a strategy the agent can use to maximize the expected cumulative reward over time.


## Assumptions

1. **Fully Observable Environment**: We assume that the environment is fully visible to the agent (variations do exist, which we can explore later).
2. **Non-IID Data**: In the case of RL, data is typically not independent and identically distributed (IID).

Let's think about the second assumption. In the **supervised learning** paradigm, we collect data points and their associated outputs. Each data point is independent of the others. 

Can we say the same for **reinforcement learning**? **No.**

**Example:**  
Suppose you're a rat in a maze with two paths:
- One path is full of traps (−ve rewards) but ends with a big cheese (+ve reward).
- The other path has smaller cheese bits and a big cheese at the end.


                c _ _ _ C
                t _ _ _ c
                t _ _ _ c
                t _ _ _ c
                _ _ r _ _


Let’s say the rat takes the left path and hits a trap. Now it sees a series of traps ahead. The observations and rewards it collects are influenced by its past decisions. This makes the data **non-IID**: the current state and reward depend on previous actions and interactions.

---

## Important Terms and Definitions

1. **Reward**  
   A scalar value (positive or negative) given by the environment. It can be provided:
   - At every step
   - Periodically
   - Only once  
   The goal of the agent is to **maximize the expected total reward**.

2. **Agent & Environment**  
   The agent interacts with the environment. Their communication includes:
   - Actions taken by the agent
   - Observations of the environment
   - Rewards provided by the environment

3. **Actions**  
   What an agent can do in the environment. There are two main types:
   
   - **Discrete actions**: A finite set of possible choices  
   - **Continuous actions**: A continuous range of values (e.g., angles, velocities)

   **Example:**  
   Suppose you have a self-driving car:
   - **Discrete**: `{ 'left', 'right' }`
   - **Continuous**: `{ 'left, 10°', 'right, -5°' }`

   Continuous actions are uncountably infinite, which makes them more complex to handle in RL algorithms.
