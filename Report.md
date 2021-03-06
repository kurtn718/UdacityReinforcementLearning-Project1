# Learning Algorithm

The code in this repository is an implementation of the DQN learning algorithm.    

The algorithm considers the environment solved when an average score is over 13 over 100 consecutive episodes.   An episode is a single playing of the game to attempt to collect as many points (yellow bananas) as possible.

For each episode, the following steps are performed:

1) Initialize environment, Set Score to 0 
2) Obtain environment state
3) Use the environment state, to determine the next action
4) Pass in the action to the environment, to determine the reward (i.e +1 for collecting a Yellow banana)
5) Repeat Steps 2-4, until either the environment informs us that game is over or quit if we go over our max number of moves (to avoid playing an infinite game)

For Step #3 the DQN algorithm is used.  Please see the below diagram for more details: 


![DQN Learning Algoritm](/dqn-learning-algorithm.png?raw=true)
Image obtained from:  https://towardsdatascience.com/introduction-to-various-reinforcement-learning-algorithms-i-q-learning-sarsa-dqn-ddpg-72a5e0cb6287


## Neural Network Architecture

Listed below is a diagram outlining the Neural Network used in the DQN algorithm.   It consists of a fully connected network with one input node per observation state (37 nodes), connected to 2 levels of hidden layers (64 nodes each), connected to an output layer (4 nodes) - 1 node per available action.

![Neural Network Architecture](/Neural-Network-Architecture.png?raw=true)


## Neural Network Parameters

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




