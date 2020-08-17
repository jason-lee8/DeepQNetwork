# Reinforcement Learning Overview
Reinforcment Learning, one of the three branches of Deep Learning, is the study of how to make software agents learn how to do something by trial and error. Specifically, it's the study of teaching a software agent to make sequences of decisions that maxamizes the environment's cumulative reward.

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
  - 
