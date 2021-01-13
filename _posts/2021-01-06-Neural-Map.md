---
layout: post
title: "Neural Map: Structured Memory for Deep Reinforcement Learning"
date: 2021-01-06
categories: Reinforcement_Learning
tags: [Reinforcement Learning, Opensource, Framework]
---



Ruslan Salakhutdinov(professor of computer science at the Carnegie Mellon University and director of AI research at Apple)의 ([세미나](https://youtu.be/Uj9cPQXaWrw))를 요약 정리해보았다. 



# Supervised Learning

* Most deep learning problems are posed as supervised learning problems: mapping and input to to an output
  : 대부분의 문제는 지도학습(입력을 출력으로 mapping)으로 정의한다.
* Environment is typically static
  : 문제환경은 대부분 정적이다.

* Typically, outputs are assumed to be independent of each other
  : 보통, 출력들은 서로 독립적이라고 가정한다.



# Environments for RL

* Environments are dynamic and change over time
  : 환경은 동적이며 시간이 지남에 따라 변한다.
* Actions can affect the environment with arbitrary time lags
  : Action은 현재뿐만 아니라 이후의 시간에도 영향을 끼친다
* labels can be expensive of difficult to obtain
  : label(reward)를 얻기가 힘들다.



# Reinforcement Learning

* Instead of a label, the agent is provided with a reward signal:
  - High reward == good behavior
* RL produces policies
  * Map observations to actions
  * Maximize long-term reward
* Allows learning purposeful behaviors in dynamic environments



# Deep Reinforcement Learning

* Use a deep network to parameterize the policy
* Adap parameters to maximize reward using:
  - Q-learning
  - Actor-Critic
  - Evolution Strategies



# Deep Reinforcement Learning with Memory

* Can we learn an agent with a more advanced external memory
  - Neural Turing Machine
  - Differential Neural Computers
* Challenge: Memory Systems are difficult to train, especially using RL



# Why is Memory Challenging?

* Suppose an agent is in a simple random maze:
  * Agent starts at top of map
  * An agent is shown an indicator near its initial state
  * The color of the indicator determines what the correct goal is 

* At the start, no a priori knowledge to store color into memory
* The folowing must hold:
  * Write color to memory at the start of maze
  * Never overwrite memory of the color over T times steps
  * Find and enter the goal

* **Solution**: Write everything into memory



# Memory Networks

* Store(key, value) representations for the last M frames

* At each time step:
  * Perform a read operation over their memory databse
  * Write the latest percept into memory
  * Easy to learn: Just store as much as possible!

* Can be inefficient:
  * We need M> time horizon of the task (can't know this a prior)
  * We might store a lot of useless/redundant data
* Time/space requirements increase with M