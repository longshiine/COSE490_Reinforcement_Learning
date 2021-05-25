# COSE490_Reinforcement_Learning
## Summary
**COSE490: Understand the fundamentals of Reinforcement Learning, and basic techniques**  
전산학특강(강화학습)에 대한 정리 repository입니다.  
Basic RL 기법부터 DQN 까지의 과제 수행 내역들을 담고 있습니다.  

## Contents
### 1. Basic RL
**Goal:** The goal of the first homework is (i) to let the student familiar with the simulator environment, called Open AI Gym, and (ii) to understand the basic programming structure for the RL.  
**Tasks:** Use the provided file, and run the program in there. Understand how one can implement policy evaluation, policy improvement, policy iteration, and value iteration.
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
 (One exception: if you want, you may modify “online_rollout” too.). 
- Task 2: Make all the program run without error. We may test your code with different environments or different base policies (under which, your program has to work
without error for full grade.)

### 3. DQN with taxi
**Goal:** The goal of the third homework is to practice D-eep Q Network (DQN).  
- (i) In previous homework, you implemented lookup table to save values of state-action
pairs. This was possible because state-action space was small.
- (ii) In this homework, you train the agent with DQN algorithm which use neural
networks to approximate Q function.
**Tasks:** Use the provided notebook file, and complete the functions.
- In this homework, we use taxi environment (“Taxi-v3”) provided by Open AI Gym. Find the environment details at  
    https://github.com/openai/gym/blob/master/gym/envs/toy_text/taxi.py
(Detailed descriptions and codes are also provided in the first cell of given notebook.) The goal of this environment is to control taxi to pick up a customer and get to destination.  
<img width="204" alt="img4" src="https://user-images.githubusercontent.com/70363646/119445144-56c58b00-bd67-11eb-8188-acfc301d43ca.png">. 
- We consider 5x5 space with total 25 “squares”, in which there are four designated “locations” in the grid world indicated by R(ed), G(reen), Y(ellow), and B(lue). When the episode starts, the taxi starts off at a random square and the passenger is at a random location. The taxi drives to the passenger's location, picks up the passenger, drives to the passenger's destination (another one of the four specified locations), and then drops off the passenger. Once the passenger is dropped off, the episode ends.  
- Observations There are 500 discrete states since there are 25 taxi positions,5 possible locations of the passenger (including the case when the passenger is in the taxi), and 4 destination locations.  
- Passenger locations  
  - 0: R(ed)  
  - 1: G(reen)   
  - 2: Y(ellow)   
  - 3: B(lue)  
  - 4: in taxi  
- Destinations:  
  - 0: R(ed)  
  - 1: G(reen)   
  - 2: Y(ellow)   
  - 3: B(lue)  
- Actions: There are 6 discrete deterministic actions:  
  - 0: move south  
  - 1: move north   
  - 2: move east  
  - 3: move west  
  - 4: pickup passenger  
  - 5: drop off passenger  
- Rewards:  
  - There is a default per-step reward of -1  
  - Delivering the passenger: +20  
  - Executing "pickup" and "drop-off" actions without passenger: -10  
- State space = (taxi_row, taxi_col, passenger_location, destination)  

- **Task 1**: Complete the main code and the training function (marked in the notebook). We recommend you to refer to the sources cited in the head of notebook. If you refer to other sources, you MUST specify those references (in the notebook as “Markdown”).  
- **Task 2**: Optimize several parameters (marked in the notebook). Even after you successfully complete Task 1, the results may not be satisfactory due to non-optimized parameters. You should delicately tune the parameters to achieve good performance.  
