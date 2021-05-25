# COSE490_Reinforcement_Learning
COSE490: Understand the fundamentals of Reinforcement Learning, and basic techniques

## Contents
### 1. Basic RL
**Goal:** The goal of the first homework is (i) to let the student familiar with the simulator environment, called Open AI Gym, and (ii) to understand the basic programming structure for the RL.  
**Task:** Use the provided file, and run the program in there. Understand how one can implement policy evaluation, policy improvement, policy iteration, and value iteration.
- Task 1: Construct program environment to run the provided program (e.g., python, jupyter notebook, and programs for RL and Open AI Gym). The provided file is in the format of “jupyter notebook”

- Task 2: Make the (provided) program run without error.

### 2. Rollout with Frozen Lake
**Goal:** The goal of the second homework is (i) to let the student familiar with implementing an RL algorithm, and (ii) to understand the online rollout algorithm.  
**Tasks:** Use the provided notebook file, and complete the function call “do_rollout”.
- We have modified the Frozen Lake (FL). See the new MDP environment descried in matrix “P” (See line 72 in [5] of the notebook file). The transitions and rewards are deterministic1. There is no hole. Instead, we consider several states that, when entering, we will get negative reward (-5 or -10). The following is the reward value for each
(state, action) – state is shown in blue and action in each direction.  
<img width="435" alt="img1" src="https://user-images.githubusercontent.com/70363646/119444613-7d36f680-bd66-11eb-9dee-b5ad965b4b32.png">
- We also provide the “basepolicy” that will be used for rollout.(See[6]ofthenotebook)
 <img width="325" alt="img2" src="https://user-images.githubusercontent.com/70363646/119444717-a8b9e100-bd66-11eb-98a9-1b69eb6f4699.png">
- Task 1: Complete the function “do_rollout”. You should not modify the other parts.
 (One exception: if you want, you may modify “online_rollout” too.)
- Task 2: Make all the program run without error. We may test your code with different environments or different base policies (under which, your program has to work
without error for full grade.)

### 3. DQN with taxi
