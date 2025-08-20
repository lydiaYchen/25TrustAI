
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
  
  - **How to reproduce** : Student should reproduce the centralized many-to-one bandit matching algorithms and results as provided in the paper. Authors implemented and test the centralized and decentralized Explore-Then-Commit and UCB alrorithms. Student will only focus on centralized part by implementing both or just focus on one of those algorithm if there isn't enough time.

  - **How to extend** : Student should focus on extending the original setting by changing the assumption on preferences. Specifically, in the extension, arm preferences are no longer given but must be learned from observed rewards, while agent preferences are known and fixed. This changes the learning objective: the learner now needs to estimate each arm's utilities for the available agents based on observed rewards over time. It makes the problem more complicated as each arm can content one or more agents. Focus on one algorithm and no need to design a new algorithm; instead, adapt the paper's algorithm to handle the new preference assumption and proof your theoretical result (regret bound).


    
- **PAPER 4.2** : Tight Regret Bounds for Stochastic Combinatorial Semi-Bandits

  - **Brief description**: The paper studies an online learning setting called stochastic combinatorial semi-bandits. In this setting, a learning agent repeatedly selects subsets of items (subject to combinatorial constraints), observes their individual stochastic rewards, and aims to maximize cumulative reward over time. The key contribution of the paper is an analysis of the CombUCB1 algorithm, a UCB-like algorithm for this setting, and the derivation of tight regret bounds that are both gap-dependent and gap-free.
 
  - **Link** : [https://proceedings.mlr.press/v38/kveton15.pdf]
  
  - **How to reproduce**: Student should reproduce the main theoretical results and experimental findings of the paper, including implementation of CombUCB1 . concretely, carefully read and understand the problem definition (Section 2), the CombUCB1 algorithm and its initialization, and the theoretical results and proofs for regret bounds. Implement CombUCB1 as described in Algorithm 1 and make some experiments.
    
  - **How to extend**:
    1.  As an extension, student could define a combinatorial matching problem as the feasible set $\mathcal{M}$, for example: a bipartite matching between two sets ( colleges and students or workers and companies), each edge (it can be the couple (college-student) or (worker-company)) has an unknown stochastic reward. Use an oracle for maximum-weight matching based on UCB estimates.  Adapt CombUCB1 to this matching problem by modifying initialization and oracle calls accordingly, and analyzing expected computational complexity. The oracle in CombUCB1 is a black box that solves an optimization problem coming from the matching formulation.
    2.  Explore non-linear reward extensions: consider submodular reward functions (e.g. diversity), or consider quadratic rewards (pairwise interaction terms), and propose how UCB estimates can be incorporated into such objectives (possibly approximate via lin-
earization or greedy algorithms).
    3. Empirically evaluate the extended algorithm on synthetic matching instances, non-linear reward scenarios and compare performance to baseline (CombUCB1 with linear reward).
    4. (Optional) Discuss how regret bounds might generalize to these settings.
  
**NB**: For both papers, students will receive a pdf with a more formal description of each paper and tasks, as well as some link that will help to understand some concept.



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


## Topic 6 : RL (Zero-Sum Games and Multi-Armed Bandits)

- **Supervisor:** Elif

- **General description:**  
  This topic covers the intersection of zero-sum games and multi-armed bandits. The multi-armed bandit framework addresses the core challenge of balancing exploration and exploitation. In contrast, zero-sum games capture adversarial strategic interactions in which one player’s gain directly corresponds to the other’s loss. The connection between these two areas becomes especially interesting when the payoff matrix is unknown and must be learned through bandit feedback from the players' chosen actions.


- **Paper 6.1**
  - **Link:** [Matrix Games with Bandit Feedback](https://proceedings.mlr.press/v161/o-donoghue21a/o-donoghue21a.pdf)
  - **How to reproduce:**
    Students should begin by implementing the algorithms proposed in the paper and then simulate and evaluate the performance of the algorithms by generating regret plots over time (Section 5). These plots will help them to present how the algorithms learn strategies compared to the theoretical guarantees.
  - **How to extend:**
    While the paper focuses on zero-sum games, one natural extension is to explore general-sum games experimentally, in order to investigate whether similar regret behaviors or convergence properties can be observed beyond the adversarial setting. Another possible direction is to study alternative feedback approaches, for example, full-bandit feedback, where players observe the entire payoff matrix after each round. Comparing these scenarios can provide valuable insights into how the feedback structures affects learning dynamics and player’s strategies.

- **Paper 6.2**
  - **Link:** [UCB Revisited: Improved Regret Bounds for the Stochastic Muti-Armed Bandit Problem](https://infotech.unileoben.ac.at/fileadmin/shares/infotech/personal-sites/Ronald_Ortner/publikationen/UCBRev.pdf) 
  - **How to reproduce:**
    This paper introduces an improved variant of the  Upper Confidence Bound (UCB) algorithm with an elimination strategy. To reproduce the results, students should first work through the derivation of the theoretical regret bounds presented in the paper. Then, they should implement the proposed algorithm and run simulations in standard MAB settings. Empirical regret should be plotted and compared against the performance of the classical UCB algorithm, with a focus on verifying whether the empirical results align with the improved theoretical bounds.
  - **How to extend:**
    Since the contribution of the paper is primarily theoretical, a natural extension is to broaden the experimental comparison. Students can implement several well-known MAB algorithms such as ETC, UCB, and EXP3 and compare them in terms of cumulative regret. After initial experiments on small number of arms, the experiments can be scaled up to a setting with a larger number of arms to see how performance changes as the action space grows. Another direction is to apply the proposed UCB algorithm to zero-sum game settings and evaluate its performance across different payoff matrices using different notions of regret.  


- Supervisor
- Paper 8.1
- Paper 8.2
- 
