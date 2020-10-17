# Learning Algorithm

## DQN Agent

A DQN agent was used to perform training.  The code for the neural network component is in dqn_agent.py  The following parameters were used:

BUFFER_SIZE = int(1e5)  # replay buffer size

BATCH_SIZE = 64         # minibatch size

GAMMA = 0.99            # discount factor

TAU = 1e-3              # for soft update of target parameters

LR = 5e-4               # learning rate 

UPDATE_EVERY = 4        # how often to update the network

## Performing training

In the Navigation Python Notebook, the agent is initialized with the State and Action sizes of the environment.

agent = Agent(state_size=37, action_size=4, seed=0)

The method dqn is responsible for performing the training.   The following parameters were used:

Maximum of 2000 episodes.  If we can not obtain a satisfactory solution we give up.

1000 maximum timesteps per episode

Episilon Start of 1.0

Epsilon Decay multiplier factor of 0.995

Minimum Epsilon value of 0.01


# Plot of Rewards

# Ideas for Future Work

## Try tuning DQN Neural Network parameters

Increasing the learning rate from 5e-4 to 5e-3, resulted in worse perfomance with the training not able to provide a satisfactory solution within 
the 2000 episode limit.  

One area to explore would be whether the other corresponding hyperparamters would need to have their value increased as well.

## Try more advanced Reinforcement Learning stategies

While the DQN approach is satisfactory in solving the problem, using Double DQN's, Dueling SQN's, or Prioritized Experience Learning Replay could provide superious results.



