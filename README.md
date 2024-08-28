### Developed By : KANISHKAR M

### Register No. 212222240044

### Date : 

# MDP REPRESENTATION

## AIM:

To represent any one real-world problem in MDP form.

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


![1](https://github.com/user-attachments/assets/d584df26-c19d-4e92-8106-5a0a3fcb0845)





## PYTHON REPRESENTATION:
```py

mdp = {
    0: {  # Initial state with specific lap time, tire wear, and fuel level
        0: [(0.7, 1, -0.1, False)],  # Stay out: slight negative reward for tire wear
        1: [(0.3, 2, 0.5, False)],  # Pit for new tires: positive reward for improving lap time
        2: [(0.2, 3, 0.0, False)],  # Change fuel strategy: neutral reward
    },
    1: {  # Slightly worn tires, lower fuel level, still racing
        0: [(0.8, 1, -0.2, False)],  # Stay out: increased tire wear, lower lap performance
        1: [(0.2, 2, 0.7, False)],  # Pit for new tires: better performance after pit
        2: [(0.3, 3, 0.0, False)],  # Change fuel strategy: neutral impact on lap time
    },
    2: {  # After a pit stop, fresh tires, better lap time
        0: [(0.6, 4, 0.8, False)],  # Stay out: new tires yield improved lap time
        1: [(0.1, 2, 0.0, False)],  # Pit again: low reward as tires are fresh
        2: [(0.2, 3, 0.0, False)],  # Change fuel strategy: moderate effect on performance
    },
    3: {  # Optimal pit stop and fuel strategy achieved, terminal state
        0: [(1.0, 4, 1.0, True)],  # Terminal state: race performance maximized
        1: [(1.0, 4, 1.0, True)],  # No further action, terminal state
        2: [(1.0, 4, 1.0, True)],  # No further action, terminal state
    }
}

```


## OUTPUT:

![image](https://github.com/user-attachments/assets/f7fc3cfb-6b90-4ba7-a957-dad7ab389e1b)



## RESULT:

Thus the given real world problem is successfully represented in a MDP form.
