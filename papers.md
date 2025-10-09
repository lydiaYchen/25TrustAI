
#  Course descriptionTopics, papers, and supervisors

## Topic 1: GenAI 

- **Supervisor** Gert Lek
- **General description :** AI-generated images are increasingly hard to distinguish by eye, and the political and safety consequences pose significant risks to trust in digital media, elections, and public discourse. This topic studies training-free detection of AI-generated images using vision foundation models to improve our ability to detect synthetic content.

- **Paper 1.1** Further improving training-free AI-generated image detection.

  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐⭐
  
  - **Link :** [Understanding and Improving Training-Free AI-Generated Image Detections with Vision Foundation Models](https://arxiv.org/abs/2411.19117)
  - **Brief description :** This work examines training-free detection of AI-generated images by analyzing how robust different their vision foundation model embeddings are to perturbations. It shows that fake images tend to be more sensitive to perturbations (e.g. Gaussian noise) than their real counterpart. It then designs an approach to use this sensitivity to detect fake images. The authors evaluate several pre-trained foundation models and perturbations. The authors then propose two improvements to make this insight competitive in detection with trained methods. 
  - **How to reproduce :** You will be given a set of 1000 image pairs (real vs. fake). Reproduce the key experiments as follows:
    1. Implement the baseline detector (RIGID) by extracting and computing the embedding similarity.
    2. Recreate the Gaussian noise and Gaussian blur perturbation experiment.
    3. Implement the MINDER approach from the paper by taking the minimum of similarities.
       
  - **How to extend :** More recent, powerful foundation models such as DINOv3 and I-JEPA have been released since the publication. An extension would be to evaluate these using the same framework on more powerful foundation models. You can also explore alternative aggregation schemes on the similarities instead of the mean, to use more structural information to improve performance. If we can find a new perturbation, this would be interesting, but the obvious choices for this have already been exhausted. Self-proposed extensions are also appreciated.

- **Paper 1.2** : Loss-landscape analysis of AI-generated vs. real images.

  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐⭐
  
  - **Link :** [Computational Safety for Generative AI:
A Signal Processing Perspective](https://arxiv.org/pdf/2502.12445) Section 5A
  - **Brief description :** Section V-A of this survey studies training-free detection of AI-generated images. It uses the above approach but visualises the loss-landscape in the vision foundation model embedding space. This visual is compared with its real counterpart. The insight here is that the synthetic images have a very specific and distinct loss-landscape vs. real images. 
  - **How to reproduce :** You will be given a set of 1000 image pairs (real vs. fake). Reproduce the key experiments:
    Select a subset of the real and generated images from several diffusion models and recreate their 2d loss-landscape visual. This is achieved by computing cosine similarities over different noise intensities. Create multiple graphs with varying settings of noise in each graph. 
  - **How to extend :** We conjecture that increased realism in more recent and powerful diffusion models has reduced the sensitivity difference. Thus the loss landscape of fake images should converge to that of the real images. You can investigate if this is indeed the case. This conjecture has important consequences: If true, images would become increasingly harder to detect. But if false, synthetic images look more realistic but carry the same artifacts that tell them apart from real images. Therefore, you will get data sets from more and less modern diffusion models and compare their loss-landscapes. A follow-up is to see when the conjecture is true, if more powerful foundation models restore the difference in the loss landscape. Self-proposed extensions are also appreciated.

## Topic 2 : RL (Trust-Aware and Differentially Private Multi-Armed Bandits)

- **Supervisor:** Elif
- **Email**: elif.yilmaz@unine.ch

- **General description:**  
  This topic covers multi-armed bandit (MAB) algorithms with a focus on incorporating additional considerations such as trustworthiness and differential privacy. Students will investigate both standard and trust-aware/differentially private MAB algorithms, understanding how trust/differential privacy dynamics influence decision-making and regret performance. Through simulations and experiments, students will gain experience in evaluating algorithm performance under different environments and constraints. Overall, the topic emphasizes both the theoretical foundations and practical implementation challenges of MAB algorithms.

- 👨‍🏫: ⭐⭐
- 🖥️: ⭐

- **Paper 2.1**
  - **Link:** [Minimax-optimal trust-aware multi-armed bandits](https://arxiv.org/pdf/2410.03651)
  - **How to reproduce:**
    Students should begin by implementing the standard UCB algorithm and then the trust-aware UCB algorithm proposed in the paper (Section 3.2). They should reproduce the experimental setup by simulating environments (Section 5). Then, they should compare the performance of both algorithms by generating regret curves and analyzing whether the empirical results align with the theoretical regret bounds.
  - **How to extend:**
    Students can extend the paper by experimenting with a larger number of arms or running the algorithms over longer time horizons to test scalability. Another interesting extension is to design alternative models of trust update mechanism or alternative action recommendation based on trust level and compare performance against the original setup. On the other hand, they can implement different MAB algorithms such as ETC and apply trust-aware mechanism. Thus, students might better understand under which conditions trust-aware MABs provide the most benefit. 

- **Paper 2.2**
  - **Link:** [Algorithms for Differentially Private Multi-Armed Bandits](https://arxiv.org/pdf/1511.08681) 
  - **How to reproduce:**
    This paper proposes a differentially private version of UCB in stochastic multi-armed bandit setting. To reproduce the results, students should implement the private UCB algorithm, then run simulations. Regret curves should be compared against the standard UCB and its private variants (section 4) and thus the regret bound should be verified.
  - **How to extend:**
    Students can implement other multi-armed bandit algorithms such as ETC, UCB and EXP3 to better understand baseline methods. They can apply similar differential privacy notions to different MAB algorithms to compare them with the private UCB. One direction is to evaluate its performance in larger action spaces and then compare the results. Another interesting extension is to apply the differential privacy notions to zero-sum games.





## Topic 3: GenAI

- **Supervisor:** Basile

- **General description:**
  This topic proposes considering different approaches to increase efficiency in the inference of generative models. The first subject addresses the problem of model selection under budget constraints, which has received a lot of traction lately. The second one concerns the challenge of accelerating Text-to-Image generation using alternative computer arithmetic. These subjects also contributes to AI trustworthiness by ensuring that generative models can deliver consistent results under limited computational budgets and by making the trade-offs between cost, speed, and output quality more explicit and measurable. The students will be able to use the most recent models to work on some very concrete issues of the current state of the art. They should be prepared to work on dense codebases and have a good understanding of the systems used in machine learning inference
  
- **Paper 3.1**
  - 👨‍🏫: ⭐⭐
  - 🖥️: ⭐⭐ 
  
  - Link: [PromptWise: Online Learning for Cost-Aware Prompt Assignment in Generative Models](https://arxiv.org/abs/2505.18901)
    
  - How to reproduce:
    
    Students should reproduce the proposed algorithm, focusing on the simpler task. The algorithm should run locally on publicly available models, using the inference time as cost input. They can rely on previous works' codebase for easier implementation.
    
  - How to extend:
    
    The students should consider one or several of the following extension path :   
      - Considering other modalities for the selected models, notably Text to Image generation. This requires using other models as well as considering new metrics for evaluation.
      - Using active learning to improve the prediction accuracy. Thanks to a measure of uncertainty, we can predict when to query ground truth results in order to refine the prediction of our selector.

- **Paper 3.2**
  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐⭐
  
  - Link: [MixDQ: Memory-Efficient Few-Step Text-to-Image Diffusion Models with Metric-Decoupled Mixed Precision Quantization](https://arxiv.org/abs/2405.17873)
    
  - How to reproduce:
    
    Reproduce the experimental results using the provided code. Specifically the students should ensure their results align with the value reported in the paper for SDXL.
  
  - How to extend:
    
    You can investigate one or several of the following points. Students are also welcomed to propose their ideas.  
      - Adapt the framework for undistilled models. This opens the way to state-of-the-art models but requires to design a quantization error correcting scheme more robust than the one currently proposed.  
      - Implement a caching policy to further increase sampling speed. Several caching methods already exist for diffusion models, it is yet to determine which one is the most suited to this case. 




## Topic 4: RL (Matching and Multi-Armed Bandits)  

- **Supervisor:** Andreas Athanasopoulos
- **mail**: andreas.athanasopoulos@unine.ch 

- **General description:**  
  This topic aims to explore learning algorithms in the context of matching markets. Students will specifically study matching problems, where a central platform matches agents from two distinct sets based on their preferences. For example, consider the assignment of students to universities, where a central mechanism decides the allocation.

  The papers specifically focus on learning fair (or trustworthy) outcomes of agents, where the notion of fairness is defined with respect to agents’ preferences. One important solution concept is **stable matching**, a matching where we cannot find a pair of agents who both prefer each other over their current partners. Stable matchings respect agents’ preferences and connect to the concept of equilibrium in game theory, since no pair of agents has an incentive to deviate from the market.

  This topic represents a paradigm of multi-agent learning, where multiple agents participate in a market and compete for matches. Students will study matching problems, which are central to economics (with the Nobel Prize awarded to Gale and Shapley), and their intersection with learning algorithms from **Multi-Armed Bandits (MAB)**, a core framework in reinforcement learning.



- 👨‍🏫: ⭐⭐  
  Some theoretical knowledge, particularly in multi-armed bandits, is required to fully understand the papers. We provide all the necessary material to ensure that students can follow along.
- 🖥️: ⭐  
  The experiments are simulation-based and can be conducted on a standard laptop.
  
- **Paper 4.1:**  **Competing Bandits in Matching Markets**  
  The paper studies learning algorithms in settings where agents are initially unaware of their preferences. More specifically, it considers a scenario in which agents learn preferences through repeated interactions with each other, formulating the problem within the Multi-Armed Bandit framework.
  - **Link:** [https://arxiv.org/abs/1906.05363](https://arxiv.org/abs/1906.05363)  
  - **How to reproduce:**  
    To reproduce the paper, students should first implement classic Multi-Armed Bandit algorithms, specifically Explore-Then-Commit (ETC) and Upper Confidence Bound (UCB). Then, they should adapt these base algorithms to matching markets and replicate the experiments presented in the paper.  
  - **How to extend:**  
    1. Provide experiments on randomly generated examples and plot the regret of the proposed algorithm.
    2. Provide experiments where both sides of the market are initially unaware of their preferences.  
    3. An interesting extension is to perform experiments that empirically quantify the algorithm’s performance in the case of non-truthful agents (Section 3.3 of the paper). While the paper studies this theoretically, many questions remain regarding the extent to which an agent can exploit rewards. Initial experiments would be valuable for students and could potentially lead to a thesis. Additionally, students can research related literature to complement their work.  

- **Paper 4.2:** **Learning Equilibria in Matching Games with Bandit Feedback** (Challenging)     
The paper extends the previous work by considering interactions that occur after agents are matched. For example, after students are assigned to universities, students can choose their level of effort while universities can adjust the academic environment. These post-matching interactions are modeled as a zero-sum game, and the paper studies algorithms that learn the equilibrium in this setting.

  - **Link:** [https://arxiv.org/abs/2506.03802](https://arxiv.org/abs/2506.03802)  
  - **How to reproduce:**  
    To reproduce the paper, students should first implement a Upper Confidence Bound (UCB) algorithm for zero-sum games. Then, they can extend the UCB algorithm according to the paper and reproduce the experiments.  
  - **How to extend:**  
    1. Empirically study alternative regret measures, such as player-optimal and player-pessimal regret, independent of the matching instability studied in the paper.
    2. Conduct experiments in decentralized models. This requires students to study additional papers on decentralized matching models and perform initial experiments. Specifically, students can investigate different interaction protocols with additional feedback and analyze the system’s regret.
    3. For highly motivated students, several directions for future research can be explored.

## Topic 5: RL
- **Supervisor** : Hortence Nana
  
- **PAPER 5.1** : Bandit Learning in Many-to-One Matching Market
  
  - 👨‍🏫: ⭐⭐
  - 🖥️: ⭐⭐
  
  - **Brief description** : The paper considers a matching markets (like students to schools , doctors to hospitals or workers to     companies) where there are many agents and fewer arms (schools/companies), and each arm can take multiple agents (capacity). Agents learn over time which arms they like because rewards are uncertain or unknown. So it's multi-armed bandits, but with matching and stability rules.
  
  - **Link** : [https://openreview.net/pdf?id=rLuT4vG7NsO]
  
  - **How to reproduce** : Student should reproduce the centralized many-to-one bandit matching algorithms and results as provided in the paper. Authors implemented and test the centralized and decentralized Explore-Then-Commit and UCB alrorithms. Student will only focus on centralized part by implementing both or just focus on one of those algorithm if there isn't enough time.

  - **How to extend** : Student should focus on extending the original setting by changing the assumption on preferences. Specifically, in the extension, arm preferences are no longer given but must be learned from observed rewards, while agent preferences are known and fixed. This changes the learning objective: the learner now needs to estimate each arm's utilities for the available agents based on observed rewards over time. It makes the problem more complicated as each arm can content one or more agents. Focus on one algorithm and no need to design a new algorithm; instead, adapt the paper's algorithm to handle the new preference assumption and proof your theoretical result (regret bound).


    
- **PAPER 5.2** : Tight Regret Bounds for Stochastic Combinatorial Semi-Bandits

  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐⭐

  - **Brief description**: The paper studies an online learning setting called stochastic combinatorial semi-bandits. In this setting, a learning agent repeatedly selects subsets of items (subject to combinatorial constraints), observes their individual stochastic rewards, and aims to maximize cumulative reward over time. The key contribution of the paper is an analysis of the CombUCB1 algorithm, a UCB-like algorithm for this setting, and the derivation of tight regret bounds that are both gap-dependent and gap-free.
 
  - **Link** : [https://proceedings.mlr.press/v38/kveton15.pdf]
  
  - **How to reproduce**: Student should implement the CombUCB1 . concretely, carefully read and understand the problem definition (Section 2), the CombUCB1 algorithm and its initialization, and the theoretical results and proofs for regret bounds. Implement CombUCB1 as described in Algorithm 1 and make some experiments.
    
  - **How to extend**: As extention, student will just find a simple use case application and apply it there.
   
  
**NB**: For both papers, students will receive a pdf with a more formal description of each paper and tasks, as well as some link that will help to understand some concept.

## Topic 7: GenAI (Sampling in graph synthesizers)
- **Supervisor:** Abele Malan

- **General description:**
  Investigate output controllability and process optimization in the sampling of iterative denoising (e.g., diffusion) deep learning models for synthetic graph generation.
  Ensuring that one can control a trained model on demand with specific rules is a key prerequisite to ensuring the trustworthiness of its output.
  Similarly, tweaking the sample generation process to optimize for desirable properties helps maximize confidence in the ability of models to generate reliable data.
  Data modeled by the graph generators encompasses structural (adjacency matrix) and, optionally, auxiliary (e.g., molecular atom and bond types) information.
  The reproducibility tasks focus on either exploring the sampling capabilities of a state-of-the-art model or techniques for conditioning sampling based on desirable properties across multiple models.
  Consequently, extensions tackle areas like generation speed/quality improvements or further increasing the complexity of targeted conditions.
  Since the work mainly concerns sampling, the longer and more resource-intensive part of training denoising models is not generally required.
  However, experiments involving new datasets or smaller auxiliary models could be an exception.
  For extensions, students should tackle at least one task.
  Working on alternative tasks is also possible, subject to approval from the teaching team.

- **Paper 6.1:** DeFoG: Discrete Flow Matching for Graph Generation
  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐
  - **Link:**
    [https://openreview.net/pdf?id=KPRIwWhqAZ](https://openreview.net/pdf?id=KPRIwWhqAZ)
  - **How to reproduce:**
    Use the provided codebase (and model checkpoints) to run the DeFoG model proposed in the paper (without the other baseline models).
    Specifically, recreate Table 1 (with 10% and 100% steps), Figure 2 (a), and all Figure 3 subfigures.
  - **How to extend:**
    - additional sample distortion functions, with the target of further boosting generation quality (MMD or validity), for (specific) test scenarios;
    - graph editing (e.g., given a graph, use the model trained on planar data to edit it into a planar version) or augmentation (e.g., given a graph structure, add the node types) instead of generation from scratch;
    - dynamic optimization of sampling parameters (distortion, target guidance, stochasticity) during generation.


- **Paper 6.2:** Diffuse, Sample, Project: Plug-And-Play Controllable Graph Generation
  - 👨‍🏫: ⭐⭐
  - 🖥️: ⭐⭐⭐
  - **Link:**
    [https://openreview.net/pdf?id=ia0Z8d1DbY](https://openreview.net/pdf?id=ia0Z8d1DbY)
  - **How to reproduce:**
    Use the codebase provided by the PRODIGY framework authors and checkpoints from the authors of the underlying tested models to replicate PRODIGY's main results.
    Specifically, recreate Table 5 (which is a variant of Table 4 with extra hyperparameter information; only the entries with PRODIGY and without the EDP-GNN model), Table 10 (which is Table 6 with additional hyperparameter information), and Table 11 (which is Table 7 with more hyperparameter information; only the QM9 dataset and again without the EDP-GNN model).
    Note that the model referred to as DruM by PRODIGY authors has since been renamed to GruM by its authors.
  - **How to extend:**
    - optimizing for more than one condition at once (the method supports such a use case, but the paper does not test it);
    - additional constraint types (e.g., control the count of other graphlets, like squares instead of triangles);
    - new partial step $\gamma_t$ formulations (possibly based on an auxiliary neural network).

*Bonus extension:* Harness classifier-free guidance in DeFoG's classifier-free guidance to dynamically steer graphs towards the closest counterpart satisfying one of the hard constraints covered in PRODIGY and analyze the obtained performance.
