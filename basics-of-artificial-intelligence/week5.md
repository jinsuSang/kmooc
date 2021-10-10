# 인공지능 기초 5주차

# 마르코프 결정 과정

## Markov Decision Processes

- A policy is a distribution over actions given states
- MDP policies depend on the current state (not the history)
- Policies are stationary (time-independent)

## Value Functions

- The state value function is the expected return starting from state s, under a plicy 파이
- The action-value function Q파이(s,a) is the expected return starting from state s, <u>**taking action a**</u>, under a policy 파이 

## Bellman Expectation Equation for MDPs

- The value function can be decomposed into two parts
  - Immediate reworad Rt+1
  - Discounted value of successor state rV(st+1)

- the state-value function can be decomposed

- the action-value function can be decomposed

- Bellman expectation equation for V파이
- Bellman expectation equation for Q파이

---

## 동적 프로그래밍을 통한 마르코프 결정 과정

- a very general solutino method for problems which have two properties

1. optimal substructure

   optimal solution can be decomposed into subproblems

2. overlapping subproblems

   subproblems recur many times

   solutions can be cached and reused

#### Markov decesion processes satisfy both properties

- Bellman equation gives recursive decomposition 
- Value function stores and reuses solutions

#### Prediction

- evaluate the future

#### Control 

- optimize the future 

### Iterative Policy Evaluation

- problem : evaluate a given policy 파이
- soluction : iteratively apply Bellman expectation backup
