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

![Plot of Rewards](/plot-of-rewards.jpg?raw=true)

| Episode  | Avg Score |
| ------------- | ------------- |
| 100  | 1.46  |
| 200  | 4.69  |
| 300  | 7.82  |
| 400  | 10.49  |
| 500  | 13.15  |
| 600  | 14.73  |
| 700  | 14.53  |
| 800  | 14.94  |
| 900  | 15.59  |
| 918  | 16.00  |

As can be seen the agent's average score (over last 100 episodes) steadily increases until we hit our desired/target average score.   There is a minor decline between episodes 500 and 600, but as can be seen it quickly recovers.

# Ideas for Future Work

## Try tuning DQN Neural Network parameters

Increasing the learning rate from 5e-4 to 5e-3, resulted in worse perfomance with the training not able to provide a satisfactory solution within 
the 2000 episode limit.  

One area to explore would be whether the other corresponding hyperparamters would need to have their value increased as well.

## Try more advanced Reinforcement Learning stategies

While the DQN approach is satisfactory in solving the problem, using Double DQN's, Dueling SQN's, or Prioritized Experience Learning Replay could be explored to see if they provide superior results.

For this project, it is probably overkill as there is no major decline in the Average score the longer the DQN is trained.   We stop the training when we hit our target, so it is possible that over a longer number of episodes the DQN performance would degrade.   Also other algorithms could potentially provide higher scores in the same number of episodes.




