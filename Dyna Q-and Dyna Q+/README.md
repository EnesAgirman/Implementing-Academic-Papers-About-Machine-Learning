# Implementing Dyna Q- and Dyna Q+

I implement the paper "Integrated Architectures for Learning, Planning, and Reacting Based on Approximating Dynamic Programming" by Richard S. Sutton. 
In this paper, 3 algorithms are compared based on 2 different tasks:
- Blocking Task: A task where a maze is given and we are trying to find the shortest path to the goal. However, at the middle of the task, the optimum path is blocked. Now, a different path to the goal must be found.
- Shortcut Task: A task where a maze is given and we are trying to find the shortest path to the goal. However, at the middle of the task, the maze is changed so that the previous path reaches the goal but there exist also a shorter path now.

To solve these tasks, 3 algorithms are used:
- Dyna Q+ (Dyna Q Algorithm with Exploration Bonus)
- Dyna Q- (Dyna Q Algorithm without Exploration Bonus)
- Dyna PI (Dyna Policy Iteration Algorithm)

In this project, I only implemented Dyna Q+ and Dyna Q- algorithms and I obtained the results given in the 7th page of paper which are the end results.

To get rid of the randomness noise, I did the same experiment for 100 times and got the average of the results. I used the same hyperparameters given in the paper
