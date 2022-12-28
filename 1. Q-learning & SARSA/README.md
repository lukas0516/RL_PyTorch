# Q-learning
**This is an implementation of Q-learning, and it is used to solve the Cliff Walking problem.**

## Description

Cliff walking is part of the [Toy Text environments](https://www.gymlibrary.dev/environments/toy_text/) in [Gym](https://www.gymlibrary.dev/).

The board is a 4 $\times$ 12 matrix, with (using NumPy matrix indexing):
* [3,0] as the start at bottom-left
* [3,11] as the goal at bottom-right
* [3,1:10] as the cliff at bottom-center

If the agent steps on the cliff, it returns to the start. An episode terminates when the agent reaches the goal.

<div align=center><img src="https://www.gymlibrary.dev/_images/cliff_walking.gif"></div>  
<div align=center><img src="https://miro.medium.com/max/1100/1*52MwrYKyzQXuKZ88rqu70A.webp"></div>  


### Actions
There are 4 discrete deterministic actions:
* 0: move up
* 1: move right
* 2: move down
* 3: move left

### Observations
There are 3 $\times$ 12 + 1 possible states. In fact, the agent cannot be at the cliff, nor at the goal (as this results in the end of the episode). It remains all the positions of the first 3 rows plus the bottom-left cell. The observation is simply the current position encoded as [flattened index](https://numpy.org/doc/stable/reference/generated/numpy.unravel_index.html)

### Reward
Each time step incurs -1 reward, and stepping into the cliff incurs -100 reward.

---
## Simulation Result
<img src="https://github.com/lukas0516/RL_PyTorch/blob/main/1.%20Q-learning%20%26%20SARSA/result.svg" width=500/>

## Dependencies
gym==0.18.3  
numpy==1.21.6  
pytorch==1.8.1  
tensorboard==2.5.0

## How to use my code
Just run **'python main.py'**.   
### Visualize the training curve
You can use the tensorboard to visualize the training curve. 

## Reference
* https://www.gymlibrary.dev/environments/toy_text/cliff_walking/
* https://towardsdatascience.com/reinforcement-learning-cliff-walking-implementation-e40ce98418d4
