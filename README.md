### Developed By : KANISHKAR M

### Register No. 212222240044

### Date : 

# MDP REPRESENTATION

## AIM:

To represent pit stop strategies in Formula 1 racing problem in MDP form.

## PROBLEM STATEMENT:

### Problem Description

### The problem involves optimizing pit stop strategies in Formula 1 racing to maximize overall race performance and minimize lap times. Teams must decide when to pit for tire changes, taking into account factors such as tire wear, fuel levels, track position, and competitor strategies. By formulating this as a Reinforcement Learning (RL) problem, we aim to train an agent that can dynamically make pit stop decisions to improve the chances of winning the race.

### State Space

The state space consists of various features that represent the current race situation, including:

1.Current lap time.

2.Tire wear level (e.g., on a scale from 0 to 100)

3.Fuel level (e.g., in liters).


### Sample State

1.Current lap time: 1:30.5

2.Tire wear: 70%

3.Fuel level: 15 liters

### Action Space
The action space includes possible pit stop decisions that the agent can take. Possible actions could be:

1.Pit for new tires.

2.Stay out on the current tires.

3.Change fuel strategy (e.g., add more fuel).

### Sample Action

Pit for new tires (switch from medium to hard tires).

### Reward Function

#### Reward of 1: Positive reward for improving lap time after a pit stop.

#### Reward of 0: Negative reward for losing positions due to a pit stop.

### Graphical Representation

![1](https://github.com/user-attachments/assets/ebb1872f-511e-4bc3-b5bf-97e01bef4c2a)


## PYTHON REPRESENTATION:
```py

mdp = {
    0: {  # Initial state
        0: [(0.5, 1, -0.1, False)],  # Stay out
        1: [(0.4, 2, 0.5, False)],  # Pit for new tires
        2: [(0.1, 3, 0.0, False)],  # Change fuel strategy
    },
    1: {  # Slightly worn tires
        0: [(0.6, 1, -0.2, False)],  # Stay out
        1: [(0.3, 2, 0.7, False)],  # Pit for new tires
        2: [(0.1, 3, 0.0, False)],  # Change fuel strategy
    },
    2: {  # After a pit stop
        0: [(0.5, 4, 0.8, False)],  # Stay out
        1: [(0.3, 2, 0.0, False)],  # Pit again
        2: [(0.2, 3, 0.0, False)],  # Change fuel strategy
    },
    3: {  # Terminal state
        0: [(1.0, 4, 1.0, True)],  # Terminal state
        1: [(1.0, 4, 1.0, True)],  # No further action
        2: [(1.0, 4, 1.0, True)],  # No further action
    }
}


```


## OUTPUT:

![image](https://github.com/user-attachments/assets/5d74bd1c-fd69-4aad-b544-881697b9e34d)


## RESULT:

Thus the pit stop strategies in Formula 1 racing problem is successfully represented in a MDP form.
