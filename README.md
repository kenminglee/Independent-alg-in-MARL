# Supplementary Material for "Independent Reinforcement Learning Algorithms in Multi-Agent Environments"

## Implementation of Algorithms
Implementations of all algorithms were based on the following open-sourced GitHub libraries/reference implementations:

- Implementation of DQN and DRON were based on the Machin library (https://github.com/iffiX/machin)
- Implementation of independent PPO was based on Stable Baselines3 (https://github.com/DLR-RM/stable-baselines3)
- Implementation of DRQN, QMIX, COMA and CommNet came from https://github.com/starry-sky6688/StarCraft
- Implementation of MADDPG came from the original code implementation: https://github.com/openai/maddpg
- Implementation of MAPPO and RMAPPO came from the original code implementation: https://github.com/marlbenchmark/on-policy

## Hyperparameters
Hyperparameters used for all algorithms are listed below:

### DQN and DRON
| Hyperparameter                   | Value          |
|----------------------------------|----------------|
| fully-connected layer dimensions | 512 x 256 |
| optimizer                        | Adam           |
| learning rate                    | 0.001          |
| discount factor                  | 0.99           |
| replay buffer size               | 1 x 10^6 |
| batch size                       | 256            |
| loss function                    | MSE            |
| initial epsilon                  | 1              |
| epsilon decay rate               | 0.9999         |
| double                           | True           |
| dueling                          | True           |
| priority                         | True           |

### PPO
| Hyperparameter                   | Value                         |
|----------------------------------|-------------------------------|
| fully-connected layer dimensions | 64 x 64                  |
| number of environments           | 4                             |
| optimizer                        | Adam                          |
| number of steps                  | episode length                |
| number of epochs                 | 10                            |
| minibatch size                   | episode length \* \# of agents \* 4 |
| discount factor                  | 0.99                          |
| GAE lambda                       | 0.95                          |
| learning rate                    | 0.0007                        |
| value function coefficient       | 0.5                           |
| clip                             | 0.2                           |
| entropy                          | 0.01                          |

### MADDPG
| Hyperparameter                   | Value          |
|----------------------------------|----------------|
| fully-connected layer dimensions | 64 x 64   |
| optimizer                        | Adam           |
| learning rate                    | 0.01           |
| discount factor                  | 0.95           |
| replay buffer size               | 1 x 10^6 |
| batch size                       | 1024           |
| critic loss function             | MSE            |
| gradient clip norm               | 0.5            |

### MAPPO and RMAPPO
| Hyperparameter                   | Value        |
|----------------------------------|--------------|
| fully-connected layer dimensions | 64$\times$64 |
| number of environments           | 4            |
| optimizer                        | Adam         |
| number of epochs                 | 10           |
| minibatch size                   | 1600         |
| discount factor                  | 0.99         |
| GAE lambda                       | 0.95         |
| learning rate                    | 0.0007       |
| value function coefficient       | 0.5          |
| clip                             | 0.2          |
| entropy                          | 0.01         |
#### RMAPPO-specific Hyperparameters
| Hyperparameter                   | Value        |
|----------------------------------|--------------|
| number of GRU layers             | 1            |
| hidden state dimension           | 64           |

### COMA, QMIX, DRQN and CommNet
| Hyperparameter                     | Value                       |
|------------------------------------|-----------------------------|
| discount factor                    | 0.99                        |
| optimizer                          | RMSProp                     |
| number of GRU layers               | 1                           |
| hidden state dimension             | 64                          |
| gradient clip norm                 | 10                          |
| batch size                         | 256                         |
#### COMA-specific Hyperparameters 
| Hyperparameter                     | Value                       |
|------------------------------------|-----------------------------|
| critic (fully-connected) dimension | 128                         |
| actor learning rate                | 0.0004                      |
| critic learning rate               | 0.003                       |
#### QMIX/DRQN-specific Hyperparameters 
| Hyperparameter                     | Value                       |
|------------------------------------|-----------------------------|
| hypernetwork dimension             | 64                          |
| learning rate                      | 0.0005                      |
| epsilon                            | linear decay from 1 to 0.05 |
| buffer size                        | 1$\times 10^6$              |

