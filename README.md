# CS370

Human vs. Machine Approaches to Solving Problems
When solving a maze, a human would typically use heuristics or trial-and-error strategies. A person might first explore obvious pathways, use memory to backtrack when hitting dead ends, and gradually refine their pathfinding based on past experience. Humans might also use mental shortcuts, like "follow the right-hand wall," to navigate mazes more efficiently.

By contrast, the pirate intelligent agent uses a deep Q-learning algorithm. Instead of intuition, it relies on numerical rewards to decide which action to take. It systematically explores actions, records the results, and uses this information to update a Q-table or Q-network. Over time, the agent learns which moves maximize its reward — reaching the treasure as fast as possible.

Similarities: Both humans and machines learn by trial and error, adjusting behavior based on past experience.
Differences: Humans use reasoning and prior knowledge; the agent only uses data from interactions with the environment, without innate "common sense."

Purpose of the Intelligent Agent in Pathfinding
The purpose of the pirate agent is to find an optimal path to the treasure while avoiding obstacles and minimizing steps. It must learn to make efficient choices through reinforcement learning rather than following hardcoded rules.

In reinforcement learning, two core strategies are exploitation and exploration:

Exploration: Trying new actions to discover if they lead to better rewards.

Exploitation: Choosing known actions that already yield good rewards.

For this pathfinding problem, an ideal balance would be initially favoring exploration (about 70–80% exploration at the start) and gradually shifting toward exploitation (around 90% exploitation later).
This way, the agent can map the environment first and then focus on refining its optimal path ([Sutton & Barto, 2018]).

Reinforcement learning helps by assigning rewards when the agent makes progress toward the treasure, thus reinforcing good actions and discouraging inefficient ones. Over many episodes, the pirate agent "learns" the fastest route.

Deep Q-Learning Implementation
In this project, deep Q-learning was used to solve the maze pathfinding problem by approximating the Q-values with a neural network. Here's the key process:

State Representation: The agent’s environment (position, obstacles, treasure location) is represented numerically as an input to the network.

Neural Network: A simple model with dense layers was trained to predict the Q-values for each possible action in each state.

Action Selection: During training, the agent used an ε-greedy policy — sometimes choosing random actions (exploration) and other times choosing the best-known action (exploitation).

Training: After each action, the agent updated its Q-network by minimizing the loss between predicted Q-values and the target values calculated using the Bellman equation.

Through hundreds or thousands of episodes, the pirate learned to consistently find the shortest path to the treasure.

References
Sutton, R. S., & Barto, A. G. (2018). Reinforcement Learning: An Introduction (2nd ed.). MIT Press.

Francois-Lavet, V., Henderson, P., Islam, R., Bellemare, M. G., & Pineau, J. (2018). An Introduction to Deep Reinforcement Learning. Foundations and Trends in Machine Learning.
