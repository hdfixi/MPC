# Deep Reinforcement Learning 

Repository implementing deep reinforcement learning and conducting experiments on the OpenAI environments

## Setup

```bash
# Clone repo
git clone git@github.com:eugeneyan/deep_rl.git && cd deep_rl

# Create conda environment
conda env create -f=environment.yml

# Activate environment
source activate deep_rl
```

### box2D errors

If a box2D error is encountered (e.g., AttributeError: module '_Box2D' has no attribute 'RAND_LIMIT_swigconstant'), please follow the steps below:  

```bash
pip uninstall Box2D box2d-py
git clone https://github.com/pybox2d/pybox2d
cd pybox2d/
python setup.py clean
python setup.py build
python setup.py install
```

More details here: <https://github.com/openai/gym/issues/100>

## Environments

Currently, the following environments are supported:

* [CartPole](https://gym.openai.com/envs/CartPole-v0/)
* [LunarLander](https://gym.openai.com/envs/LunarLander-v2/)

## Models

* Deep Q-Network (vanilla) [`dqn_plain.py`](models/dqn_plain.py)
* Deep Q-Network (with target network) [`dqn.py`](models/dqn.py)
* Double Deep Q-Network [`ddqn.py`](models/ddqn.py)

## Running experiments

Running experiments is a simple as 

```bash
# To run experiment on cartpole environment
python cartpole_runner.py

# To run experiment on lunar lander environment 
python lunarlander_runner.py
```

### Usage

```bash
python lunarlander_runner.py --help

usage: lunarlander_runner.py [-h] [--model MODEL] [--render-env RENDER_ENV]
                             [--render-freq RENDER_FREQ]

optional arguments:
  -h, --help            show this help message and exit
  --model MODEL         DeepRL model to use (options: dqn_plain, dqn, ddqn;
                        default: ddqn)
  --render-env RENDER_ENV
                        Whether to render the environment (default: y)
  --render-freq RENDER_FREQ
                        How frequently to render the env (default: 500)
                        --render-env must be set to "y" to render environment
```



