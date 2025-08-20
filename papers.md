
#  Course descriptionTopics, papers, and supervisors

## Topic 1: GenAI 
- Supervisor: Basile
- Paper 1.1 (title)
  - Link
  - How to reproduce
  - How to extend
- Paper 1.2
  - Link
  - How to reproduce
  - How to extend


## Topic 2: RL (Matching and Multi-Armed Bandits)  

- **Supervisor:** Andreas Athanasopoulos  

- **General description:**  
  This topic aims to explore learning algorithms in the context of matching markets. Specifically, it considers a multi-agent learning scenario where multiple agents participate in a market and compete for their matches. Technically, students will study matching problems, which are central to economics (Nobel Prize awarded to Gale and Shapley), and their intersection with learning algorithms from Multi-Armed Bandits (MAB), a central framework in reinforcement learning.  

- **Paper 2.1**
  - **Link:** [https://arxiv.org/abs/1906.05363](https://arxiv.org/abs/1906.05363)  
  - **How to reproduce:**  
    To reproduce the paper, students should first implement classic Multi-Armed Bandit algorithms, specifically Explore-Then-Commit (ETC) and Upper Confidence Bound (UCB). Then, they should adapt these base algorithms to matching markets and replicate the experiments presented in the paper.  
  - **How to extend:**  
    An interesting extension is to perform experiments that empirically quantify the algorithm’s performance in the case of non-truthful agents (Section 3.3 of the paper). While the paper studies this theoretically, many questions remain regarding the extent to which an agent can exploit rewards. Initial experiments would be valuable for students and could potentially lead to a thesis. Additionally, students can research related literature to complement their work.  

- **Paper 2.2** (Challenging) 
  - **Link:** [https://arxiv.org/abs/2506.03802](https://arxiv.org/abs/2506.03802)  
  - **How to reproduce:**  
    To reproduce the paper, students should first implement a Upper Confidence Bound (UCB) algorithm for zero-sum games. Then, they can extend the UCB algorithm according to the paper and reproduce the experiments.  
  - **How to extend:**  
    1. Empirically study alternative regret measures, such as player-optimal and player-pessimal regret, independent of the matching instability studied in the paper.
    2. Conduct experiments in decentralized models. This requires students to study additional papers on decentralized matching models and perform initial experiments. Specifically, students can investigate different interaction protocols with additional feedback and analyze the system’s regret.
    3. For highly motivated students, several directions for future research can be explored.



## Topic 3: GenAI
- Supervisor: Gert
- Paper 3.1
  - Link
  - How to reproduce
  - How to exte
- Paper 3.2
  - Link
  - How to reproduce
  - How to exte


## Topic 4: RL
- **Supervisor** : Hortence Nana
  
- **PAPER 4.1** : Bandit Learning in Many-to-One Matching Market
  
  - **Brief description** : The paper considers a matching markets (like students to schools , doctors to hospitals or workers to     companies) where there are many agents and fewer arms (schools/companies), and each arm can take multiple agents (capacity). Agents learn over time which arms they like because rewards are uncertain or unknown. So it's multi-armed bandits, but with matching and stability rules.
  
  - **Link** : [https://openreview.net/pdf?id=rLuT4vG7NsO]
  
  - **How to reproduce** : Student should reproduce the centralized many-to-one bandit matching algorithms and results as pro-
vided in the paper. Authors implemented and test the centralized and decentralized Explore-Then-Commit and UCB alrorithms. Student will only focus on centralized part by implementing both or just focus on one of those algorithm if there isn't enough time.

  - **How to extend** : Student should focus on extending the original setting by changing the assumption on preferences. Specifically, in the extension, arm preferences are no longer given but must be learned from observed rewards, while agent preferences are known and fixed. This changes the learning objective: the learner now needs to estimate each arm's utilities for the available agents based on observed rewards over time. It makes the problem more complicated as each arm can content one or more agents. Focus on one algorithm and no need to design a new algorithm; instead, adapt the paper's algorithm to handle the new preference assumption and proof your theoretical result (regret bound).


    
- **PAPER 4.2** : Tight Regret Bounds for Stochastic Combinatorial Semi-Bandits

  - **Brief description**: 
 
  - **Link** : 
  
  - **How to reproduce**
  - **How to extend**
  
**NB**: For oth topics, students will receive a pdf with a more formal description of paper and task, as well as some link that will help to understand some concept.



## Topic 5: GenAI
- Supervisor: Abel
- Paper 1.1
  - Link
  - How to reproduce
  - How to exte
- Paper 1.2
  - Link
  - How to reproduce
  - How to exte


## Topic 6 : RL
- Supervisor: Elif
- Paper 2.1
  - Link
  - How to reproduce
  - How to exte
- Paper 2.2
  - Link
  - How to reproduce
  - How to exte



- Supervisor
- Paper 8.1
- Paper 8.2
- 
