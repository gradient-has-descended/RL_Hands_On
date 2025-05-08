#### Introduction to Reinforcement Learning ####

Given an agent, an evironment, a set of actions and the associated reward an agent can earn for each action an agent can take in that environment, reinforcement learning allows us to learn a policy, a strategy an agent can use to maximize the expected cumulative reward the agent can earn over time. 

Assumptions : 1. We assume that the enviroment is fully visible to the agent (variations do exist and we can see them later).
              2. In the case of RL, data is typically not independent and identically distributed

Let's think about our second assumption for a bit. In supervised learning paradigm, we collect data points and the associated output and the output for one data point is independent of the output of the other data points since it's not affected by them. Can you say the same for RL? NO. Let's say that your are a rat in a maze and there are 2 distinct paths, one path full of traps(-ve rewards) with cheese(+ve reward) at the end. On the other path there are smaller cheese bits and a big cheese at the end. Let's see an actual example.

                  c _ _ _ C
                  t _ _ _ c
                  t _ _ _ c
                  t _ _ _ c
                  _ _ r _ _

Let's assume that the rat takes the left path and goes through one trap. Now all it observes in front of it are a series of traps. If we collect observations and rewards, the output of the policy will directly depend on our previously taken steps, so the datapoints in our case is not IID. RL data is non-IID because the current state and reward are a result of your past interactions.


#### Important Terms and Definitions ####

1. Reward - A scalar +ve or -ve value given by the environment to the agent periodically, at every action or once in a lifetime. The goal of the agent is to maximise the expected total reward.

2. Agent & Environment - Pretty self explanatory. The agent interacts with the environment, with modes of communication between them being rewards that environment gives, actions an agent can take and observations an agent can record about the environment, the action it took, and the reward it received.