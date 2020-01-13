# Deep Deterministic Policy Gradient (DDPG)
  
## Algorithm
For this project, the _ddpg-pendulum_ algorithm provided by Udacity was adapted to train the 20 agent enviroment.   
The [DDPG](https://spinningup.openai.com/en/latest/algorithms/ddpg.html#id1) algorithm is an policy based method that implements and actor-critic archicteture.  

The pseudocode is [described](https://spinningup.openai.com/en/latest/algorithms/ddpg.html#pseudocode) as follows:  
 ![Pseudocode](/image/pseudocode.png)  
  
The code is available ate the _ddpg_agent.py_ file  
  
## Archicteture
Actor  
 - Input: (input, 128)   
 - BatchNorm(128) - ReLU  
 - Hidden: (128, 64) - ReLU  
 - Output: (64, action_size=4) - TanH  
   
Critic
 - Input: (input, 128) 
 - BatchNorm(128) - ReLU
 - Hidden: (128, 64) - ReLU
 - Output: (64, 1)  
   
 ## Hyperparameters  
BUFFER_SIZE = int(1e5)  # replay buffer size  
BATCH_SIZE = 128        # minibatch size  
GAMMA = 0.99            # discount factor  
TAU = 1e-3              # for soft update of target parameters  
LR_ACTOR = 2e-4         # learning rate of the actor   
LR_CRITIC = 2e-4        # learning rate of the critic  
WEIGHT_DECAY = 0        # L2 weight decay  
  
## Rewards
The resulting plot of the rewards during the trainings is as follows:  
![Pseudocode](/image/results.PNG)

## Future work  
Trying to optimize the hyperparameters in a more controlled way, and implementing the one version agent.
