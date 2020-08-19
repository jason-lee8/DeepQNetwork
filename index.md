## This page provides a general explanation of what reinforcement learning (RL) is, along with how we can use Q-learning, a type of reinforcement learning, to play Atari games. 

# General Overview of Deep Reinforcement Learning
Reinforcment learning is one of the three main branches of Deep Learning. It involves the study of how to make software agents learn the optimal way of acomplishing something by utilizing trial and error.

Reinforcement learning has some pretty awesome capabilities! Here is a list of some of its impressive achievements:
- In December 2013, DeepMind published a paper about how they were able to use DQNs to achieve a higher than human level performance in Atari games.
- In March 2016, DeepMind's reinforcement learning algorithm, called AlphaGo, beat 18-time world champion Lee Sedol in the game of Go. To get a sense of how impressive this is, consider that there are more possible Go game boards than atoms in the visible universe!
- 2019 was an exciting year:
  - **DeepMind's AlphaStar** was not only able to beat two of the best Starcraft players in the world, but it was also able to consistently play at the Grandmaster level.
    - Trained on over 200 years worth of real-time Starcraft play.
  - **OpenAi Five** became the world's best Dota 2 player.
    - Trained on 180 years worth of games against itself.
  - Both these algorithms were able to beat pro level players by developing new, never seen before strategies.
  - Also note that both these games' action spaces are incredibly high. For every step in Starcraft, the agent can take up to 10<sup>26</sup> steps.

---
## Key Concepts:

![alt_text](https://www.researchgate.net/profile/Richard_Csaky3/publication/323587007/figure/fig12/AS:601281001435137@1520367970912/The-reinforcement-learning-framework-Sutton-and-Barto-1998.png)

#### Note: Reinforcement learning contains lost of fancy vocabulary (jargon) so if you don't know what a word means, I made a list of key terms at the bottom.

The goal of reinforcement learning is to create an algorithm that will efficiently allow an agent to learn which (sequence of) decisions will maxamize it's cumulative reward.

- **Environment** - The world that the agent lives in. In most cases, whenever the agent takes an action, the environment's **state** will change. At every single step, an **observation** is passsed to the agent. 
  - An **observation** is what the agent can "see" in the environment. 
  - Some environments are **fully observable**, which means that the observation contains all the information in the current state. Chess is a fully observable environment because at any given moment, the agent knows where all the pieces are on the board and whos turn it is.
  - Other environments are only **partially observable** - the agent does not receieve the full information from the environment. <br> The card games, Poker and Uno, are partially observable environments because players cannot (or are not supposed to be able to) see the other player's cards.
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

## Key Terms:
- **environment** - The world that the agent lives in and interacts with.
- **agent** - The agent lives in and interacts with the environment. You can think of it as the controller or player.
  - The agent's goal is to maxamize the cumulative reward
- **state** - Every different situation that the agent encounters in the environment. 
  - Environments can often have an endless amount of states, far too many to create a rememberization table of all the states. This is what inspired the formulation of Deep Reinforcement learning.
- **Reward** - A signal that the environment sends to the agent, basically describing how good or bad being in the current state is.
  - **Return** - The cumulative reward or summed reward for one game.
- **Policy** - A function that maps an inputted state to a vector of probabilities of which action to take. In math equations, the policy is denoted by π.
  - **Optimal policy** - The stradegy that maxamizes the return. It is possible to have several optimal policies. 

---
 
# Q-Learning
Q-Learning is a type of model-free, temporal difference reinforcement learning algorithm. This might sound complex, but it's really not. Model-free means it is able to be used in almost any environment, except it is less sample efficient. Value-based It learns how to approximate ![alt_text](https://quicklatex.com/cache3/dc/ql_267ba1b21b5b36f155822ad1de969bdc_l3.png), which called the **action-value function**. 

The goal of Q-learning is to find the **optimal action value function**, which in math is written as: ![alt_text](https://quicklatex.com/cache3/5d/ql_305677770a07ea29d0687ce12ff01b5d_l3.png) 

The star/asterisk (*) indicates that the function finds the value that optimizes the action-value function. 

In math, this is written as: ![alt_text](https://quicklatex.com/cache3/16/ql_9fe1636ec802e389df42c3994e0f5e16_l3.png)



