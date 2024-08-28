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

The state space consists of all possible combinations of the game score and the foul status. Each state is represented by:

> Game Score: The current score of the game.
<br>

> Foul Status: Indicates whether a foul has occurred

### Sample State

(Game Score = 3, Foul Status = True(1))

### Action Space
The action space consists of the following actions:

1.Provide Score: Update or confirm the game score.

2.Call Foul: Indicate that a foul has occurred.

3.Do Nothing: Take no action.

### Sample Action

Call Foul

### Reward Function

#### Reward of 1: If the umpire calls a foul when a foul has occurred and provides the score.

#### Reward of 0: If the umpire either does not provide the score or fails to call a foul when a foul has occurred.

### Graphical Representation


![Img](https://github.com/user-attachments/assets/23c283e1-dc60-4a6f-b942-efd0b7d60d66)




## PYTHON REPRESENTATION:
```py

mdp = {
    0: {  # Initial state with no score and no foul
        1: [(0.8, 2, 1.0, False)],  # Higher chance of scoring with a foul
        0: [(1.0, 1, 0.0, False)]  # Guaranteed transition to state 1
    },
    1: {  # Score increased, no foul called
        1: [(1.0, 3, 1.0, True)],  # Moves to terminal state with foul
        0: [(1.0, 1, 0.0, False)]  # Stays in the same state
    },
    2: {  # Score increased with a foul
        1: [(1.0, 3, 1.0, True)],  # Guaranteed transition to terminal state
        0: [(1.0, 2, 0.0, False)]  # Stays in the same state
    },
    3: {  # Terminal state
        1: [(1.0, 3, 1.0, True)],
        0: [(1.0, 3, 0.0, True)]
    }
}

```


## OUTPUT:

![image](https://github.com/user-attachments/assets/d26e9339-886c-457d-9d87-9d3c4c8a5779)


## RESULT:

Thus the given real world problem is successfully represented in a MDP form.
