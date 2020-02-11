The following are the tasks that we are doing in this project. A 5X5 grid-world environment is given and I have to build a reinforcement learning agent to navigate towards a given goal. In this project the first task is to implement a policy function. The policy function is used to determine the actions of the agent in order to get maximum reward while reaching the goal. The second task is to update the Q-table. Here, a Q-table or a Quality-table is a matrix of the states and actions taken by the agent. The final task is to implement the training algorithm to train the agent to reach the goal in an optimal cost by using the rewards and discounts to skew the results.
### Terminology
Some of the important terms related to Reinforcement Learning,
•	Agent: 		An agent is a hypothetical entity that takes actions.
•	Action: 		An action is a move that an agent can make.
•	Environment: 	It is the canvas in which the agent takes action.
•	State: 		It is the immediate situation in which the agent finds itself.
•	Reward: 	It is the feedback given by the environment to the agent to determine whether a certain action of the agent is positive or negative.
•	Policy: 		It is the strategy according to which the agent behaves and decides what the next action should be based on the current state. It maps states to actions which give maximum rewards.
•	Value:		It is the long-term return value returned after adding discounts as well.
•	Q value:		It is like Value, but it also has an additional parameter ‘current action’. It refers to the long-term return of the current state acting under policy.

### 	Task 1: Implement Policy Function

In this environment the agent will act as per the set policy. A policy is a function that maps a given state to probabilities of selecting each possible action from that state.
For the first time the agent does not know the rewards and hence starts at random in search of a pattern. Later on the agent will move in the direction of more rewards and in turn learn to solve the complex problem.

 
Here,   π = policy, s = state and a= action.
For example, if an agent follows policy π at time t, then π(a|s) is the probability that At=a if St=s. This means that, at time t, under policy π, the probability of taking action a in state s is π(a|s). Note that, for each state s∈S, π is a probability distribution over a∈A(s). When the agent has found a pattern to the problem it will select an action which will yield the highest reward possible.
### 	Task 2 : Update Q-table

A Q-table also known as the Quality table is used to improve the quality of results. A Q-table consists of state and action as the parameters. For every episode the Q-table gets the new action and state until it reaches the goal. It does so by increasing its rewards and hence the results. 
Here the Q-table is updated after each episode and this updated Q-table is further used.

### 	Task 3 : Training Algorithm
Step one is that we initialize our environment, i.e., OpenAI’s gym environment. Our environment has three methods: 1) reset 2) step and 3) render. The reset method is used to initialize the environment with a fresh episode and the step method takes an action as a parameter, processes the action, and returns the new state, the reward for performing the action, and a boolean indicating if the run is over. Now, we’ll train our agent for a fixed number of episodes and update the state, action, reward, and next state for each episode. We’ll use an exploration rate or epsilon so that at first we’ll let our agent to try all kinds of things before it starts to see the patterns. When its not deciding the action randomly, the agent will predict the reward value based on the current state and pick the action that will give the highest reward. To decrease the number of random action, as it goes, so we introduce an exponential-decay epsilon, that eventually will allow our agent to explore the environment. 
