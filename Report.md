# Learning Algorithm

A DQN agent was used to perform training.   The following parameters were used:

BUFFER_SIZE = int(1e5)  # replay buffer size

BATCH_SIZE = 64         # minibatch size

GAMMA = 0.99            # discount factor

TAU = 1e-3              # for soft update of target parameters

LR = 5e-4               # learning rate 

UPDATE_EVERY = 4        # how often to update the networ
k

# Plot of Rewards

# Ideas for Future Work

## Try tuning DQN Neural Network parameters

Increasing the learning rate from 5e-4 to 5e-3, resulted in worse perfomance with the training not able to provide a satisfactory solution within 
the 2000 episode limit.  One area to explore would be whether the other corresponding hyperparamters would need to have their value increased as well.






