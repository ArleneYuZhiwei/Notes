## Brief Summary
## 适合RL的问题
1.sequential decision making问题，进行序列决策（action），并有reward可以衡量action的好坏程度。 文本生成领域没有合适的指标，因此reward很难设计。
2.无label,每个action由试错后选择
### Seq2seq
Sequence Generative Adversarial Nets with Policy Gradient
推敲网络
### RL辅助学习语义向量
motivation是快速阅读
[1711.02085] Neural Speed Reading via Skim-RNN

学习文章结构，word-level的每一个时间步中，判断词组起始位置，以词组向量为单位输入段落级的LSTM中，得到最终的文章向量
更加准确捕捉到词/句的意思
Deep reinforcement learning for dialogue generation
Learning to compose words into sentences with reinforcement learning
### 使用RL对模型进行调参
调整RNN/CNN的层数或维度（谷歌NMT用了强化学习调参数）
### Text Game类别
Language Understanding for Text-based Games using Deep Reinforcement Learning

## RL与NLP
优势
1.在离散空间的文本生成和序列决策
2.goal oriented的对话系统
3.RL的优势，如可以克服其他目标函数如MLE的缺陷，可以模拟大量样本，或者借助先前经验进行学习（如DQN）等
劣势
强化学习很多时候训练是很不稳定的，本身算法像高方差，难优化

# ICML 17 RL IN NLP tutorial 笔记
## Challenges
- Sparse reward (few feedback when making decisions)
- Difficulty in reward function design
- High-dimensional action space
- High variance in training RL algorithms

## Strengthens
- Weak supervision without explicit annotations
- Trial-and-error: probabilistic exploring
- Accumulative rewards: encoding expert/prior knowledge in reward design

## Forms
- Immediate rewards
类似 teacher forcing 
- Delayed rewards
 Comparing with gold standard: BLEU\ACC\F1 
 classifier: likelihood 
 Prior/domain expertise:sparsity or continuity 
 
# Reinforcement Learning for NLP 笔记
## Approaches to RL
### Value-based RL
- Estimate the optimal value function Q(s ,a)
- This is the maximum value achievable under any policy
Value-based RL learns near deterministic policy

### Policy-based RL
- Search directly for the optimal policy PI
- This is the policy achieving maximum future reward
#### Advantages:
Better convergence properties
Effective in high-dimensional or continuous action spacesCan learn stochastic policies
#### Disdvantages:
Typically converge to a local rather than global optimum
Evaluating a policy is typically inefficient and high variance
#### Extension:
Combine with value estimation
Critic: Updates action-value function parameters
Actor: Updates policy parameters in direction suggested by critic

### Model-based RL
- Build a model of the environment
- Plan (e.g. by lookahead) using model
# CS224N 笔记
- Experience is a sequence of observations, actions, rewards
- State is a summary of experience
- RL Agent
Policy: agent’s behavior function
Value function: how good would be each state and/or action
Model: agent’s prediction/representation of the environment
## What is Deep RL?

● Use deep neural network to approximate
○ Policy
○ Value function
○ Model

● Optimized by SGD
## RL in NLP

● Article summarization
** A Deep Reinforced Model for Abstractive Summarization**
Reward: ROUGH score

● Question answering
**DCN+: MIXED OBJECTIVE AND DEEP RESIDUAL COATTENTION FOR
QUESTION ANSWERING**
Introduce F1 score as extra objective combining with
traditional cross entropy loss

● Dialogue generation
** Deep Reinforcement Learning for Dialogue Generation**
Action: infinite since arbitrary-length sequences can be generated.
State: A state is denoted by the previous two dialogue turns [𝑝i, 𝑞i].
Reward: Ease of answering, Information Flow and Semantic Coherence

● Dialogue System
● Knowledge-based QA
● Machine Translation
● Text generation

## Resources

RL for NLP(papers)   https://github.com/sunxs1101/RL-Dialog/blob/master/note.md

RL for NL(A review)  http://coai.cs.tsinghua.edu.cn/hml/media/files/reinforcement_learning-in-NLP-Huangminlie.pdf

RL for NL(A review) http://users.umiacs.umd.edu/~jbg/teaching/CSCI_7000/11a.pdf

RL for NL(A review) https://www.youtube.com/watch?v=F1hZfoh-wX4

RL for NL(A review) https://web.stanford.edu/class/cs224n/lectures/lecture16-guest.pdf

RL for NLG(Blog)    https://zhuanlan.zhihu.com/p/22385421
