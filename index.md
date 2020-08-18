## This page provides a general explanation of what reinforcement learning, along with how we can use Q-learning, a type of reinforcement learning, to play Atari games. 

# General Overview of Reinforcement Learning 
Reinforcment Learning is one of the three main branches of Deep Learning. Reinforcement Learning involves the study of how to make software agents learn the optimal way of acomplishing something by utilizing trial and error. Specifically, it's the study of teaching a software agent to make sequences of decisions that maxamizes it's cumulative reward.

---

### Key Terms in Reinforcement Learning:
- **Environment** - The world that the agent lives in. The environment will change when the agent takes an action, or sometimes it may change on its own.
  - At every step, an **observation** is passsed to the agent. An **observation** is what the agent can "see" in the environment. 
    - Some environments are **fully observable**, which means that the observation contains all the information in the current state.
      - Example: Chess is fully observable, because at any given moment, the agent knows where all the pieces are on the board and whos turn it is.
    - Other environments are only **partially observable** - the agent does not receieve the full information from the environment.
      - Example: Poker or Uno are partially observable environments because players cannot (or are not supposed to be able to) see other player's cards.
  - Along with an observation, the environment will also send a **reward signal** to the agent.
    - Basically, the **reward** determines how good or bad a state is.
  - Environments can either be **deterministic** or **stochastic**, meaning that for whatever state the agent is in, the agent can know with 100% confidence what the next state is going to be, based on the actions it takes. 
  - Other environments are **stochastic**, which means there is some amount of uncertainty involved. For example, let's say in some environment, there are two actions the agent can take: left and right. If the agent decides to go left, the environment would only let the agent go left 80% of the time and right the other 20% of the time. This is stochastic because the environment is inherently random.
- **Agent** - The agent lives and acts inside an environment.
  - The agent will take actions based on the environment's observation that will change the state of the environment.
  - Agent's goal is to maxamize cumulative reward, or **return**. 
    - The cool thing is: The agent will eventually learn to sacrafice immediate rewards if it means having a higher return. For example, an agent will learn to go workout at the gym if it means not dying an early death due to health complications.
- **Action Space** - A set of all valid actions that the agent can take in an environment.
  - There are two types of action spaces:
  - **Discrete action spaces**   - Action spaces where the number of possible actions is finite. For example, games that are played only using buttons (either pressed or not pressed), like Pong or Breakout, are discrete because there are only so many possible actions you can make.
  - **Continious action spaces** - This type of action space is where the number of possible actions is not discrete, but infinite. An example of this is driving a car: For **x** in a range from (-max_steering, max_steering), you can turn the steering wheel **x** degrees. 
- **Policy** - The agent's stradegy

---
 
# Q-Learning
Q-Learning is a type of model-free, temporal difference reinforcement learning algorithm. This might sound complex, but it's really not. Model-free means it is able to be used in almost any environment, except it is less sample efficient. Value-based It learns how to approximate ![alt_text](https://quicklatex.com/cache3/dc/ql_267ba1b21b5b36f155822ad1de969bdc_l3.png), which called the **action-value function**. 

The goal of Q-learning is to find the **optimal action value function**, which in math is written as: ![alt_text](https://quicklatex.com/cache3/5d/ql_305677770a07ea29d0687ce12ff01b5d_l3.png) 

The star/asterisk (*) indicates that the function finds the value that optimizes the action-value function. 

In math, this is written as: ![alt_text](https://quicklatex.com/cache3/16/ql_9fe1636ec802e389df42c3994e0f5e16_l3.png)
