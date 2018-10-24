# Car Racing with PyTorch
Solving the car racing problem in OpenAI Gym using Proximal Policy Optimization (PPO). This problem has a real physical engine in the back end. You can achieve real racing actions in the environment, like drifting. 

## Requirement
To run the code, you need
- [pytorch 0.4](https://pytorch.org/)
- [gym 0.10](https://github.com/openai/gym)
- [visdom 0.1.8](https://github.com/facebookresearch/visdom)

## Method
Every action will be repeated for 8 frames. To get velocity information, state is defined as adjacent 4 frames in shape (4, 96, 96). Use a two heads FCN to represent the actor and critic respectively. The actor outputs $\alpha, \beta$ for each actin as the parameters of Beta distribution. 
<center><img src="img/network.png" width="50%" /></center>
## Training
Start a Visdom server with ```python -m visdom.server```, it will serve http://localhost:8097/ by default.

To train the agent, run```python ppo.py --render```.
To test, run ```python ppo_test.py --render```.

## Performance
<center><img src="img/car_racing_ppo.png"/></center>
<center><img src="img/car_racing_demo_ppo.gif"/></center>

