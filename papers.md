
#  Course descriptionTopics, papers, and supervisors

## Topic 1: GenAI 
- **Supervisor:** Basile
- 👨‍🏫: ⭐
- 🖥️: ⭐⭐⭐
- **General description:**
  This topic proposes considering different approaches to increase efficiency in the inference of generative models. The first subject addresses the problem of model selection under budget constraints, which has received a lot of traction lately. The second one concerns the challenge of accelerating Text-to-Image generation using alternative computer arithmetic. The students will be able to use the most recent models to work on some very concrete issues of the current state of the art. They should be prepared to work on dense codebases and have a good understanding of the systems used in machine learning inference
  
- **Paper 1.1**
  
  - Link: [PromptWise: Online Learning for Cost-Aware Prompt Assignment in Generative Models](https://arxiv.org/abs/2505.18901)
    
  - How to reproduce:
    
    Students should reproduce the proposed algorithm, focusing on the simpler task. The algorithm should run locally on publicly available models, using the inference time as cost input. They can rely on previous works' codebase for easier implementation.
    
  - How to extend:
    
    The students should consider one or several of the following extension path :   
      - Considering other modalities for the selected models, notably Text to Image generation. This requires using other models as well as considering new metrics for evaluation.
      - Using active learning to improve the prediction accuracy. Thanks to a measure of uncertainty, we can predict when to query ground truth results in order to refine the prediction of our selector.

- **Paper 1.2**
  
  - Link: [MixDQ: Memory-Efficient Few-Step Text-to-Image Diffusion Models with Metric-Decoupled Mixed Precision Quantization](https://arxiv.org/abs/2405.17873)
    
  - How to reproduce:
    
    Reproduce the experimental results using the provided code. Specifically the students should ensure their results align with the value reported in the paper for SDXL.
  
  - How to extend:
    
    You can investigate one or several of the following points. Students are also welcomed to propose their ideas.  
      - Adapt the framework for undistilled models. This opens the way to state-of-the-art models but requires to design a quantization error correcting scheme more robust than the one currently proposed.  
      - Implement a caching policy to further increase sampling speed. Several caching methods already exist for diffusion models, it is yet to determine which one is the most suited to this case. 


## Topic 2: RL (Matching and Multi-Armed Bandits)  

- **Supervisor:** Andreas Athanasopoulos  

- **General description:**  
  This topic aims to explore learning algorithms in the context of matching markets. Specifically, it considers a multi-agent learning scenario where multiple agents participate in a market and compete for their matches. Technically, students will study matching problems, which are central to economics (Nobel Prize awarded to Gale and Shapley), and their intersection with learning algorithms from Multi-Armed Bandits (MAB), a central framework in reinforcement learning.  

- 👨‍🏫: ⭐⭐
  - Some theoretical knowledge, particularly in multi-armed bandits, is required to fully understand the papers. We provide all the necessary material to ensure that students can follow along.
- 🖥️: ⭐
  - The experiments are simulation-based and can be conducted on a standard laptop.
  
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
- **Supervisor** Gert Lek
- **General description :** AI-generated images are increasingly hard to distinguish by eye, and the political and safety consequences pose significant risks to trust in digital media, elections, and public discourse. This topic studies training-free detection of AI-generated images using vision foundation models to improve our ability to detect synthetic content.

- **Paper 3.1** Further improving training-free AI-generated image detection.

  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐⭐
  
  - **Link :** [Understanding and Improving Training-Free AI-Generated Image Detections with Vision Foundation Models](https://arxiv.org/abs/2411.19117)
  - **Brief description :** This work examines training-free detection of AI-generated images by analyzing how robust different their vision foundation model embeddings are to perturbations. It shows that fake images tend to be more sensitive to perturbations (e.g. Gaussian noise) than their real counterpart. It then designs an approach to use this sensitivity to detect fake images. The authors evaluate several pre-trained foundation models and perturbations. The authors then propose two improvements to make this insight competitive in detection with trained methods. 
  - **How to reproduce :** You will be given a set of 1000 image pairs (real vs. fake). Reproduce the key experiments as follows:
    1. Implement the baseline detector (RIGID) by extracting and computing the embedding similarity.
    2. Recreate the Gaussian noise and Gaussian blur perturbation experiment.
    3. Implement the MINDER approach from the paper by taking the minimum of similarities.
       
  - **How to extend :** More recent, powerful foundation models such as DINOv3 and I-JEPA have been released since the publication. An extension would be to evaluate these using the same framework on more powerful foundation models. You can also explore alternative aggregation schemes on the similarities instead of the mean, to use more structural information to improve performance. If we can find a new perturbation, this would be interesting, but the obvious choices for this have already been exhausted. Self-proposed extensions are also appreciated.

- **Paper 3.2** : Loss-landscape analysis of AI-generated vs. real images.

  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐⭐
  
  - **Link :** [Computational Safety for Generative AI:
A Signal Processing Perspective](https://arxiv.org/pdf/2502.12445) Section 5A
  - **Brief description :** Section V-A of this survey studies training-free detection of AI-generated images. It uses the above approach but visualises the loss-landscape in the vision foundation model embedding space. This visual is compared with its real counterpart. The insight here is that the synthetic images have a very specific and distinct loss-landscape vs. real images. 
  - **How to reproduce :** You will be given a set of 1000 image pairs (real vs. fake). Reproduce the key experiments:
    Select a subset of the real and generated images from several diffusion models and recreate their 2d loss-landscape visual. This is achieved by computing cosine similarities over different noise intensities. Create multiple graphs with varying settings of noise in each graph. 
  - **How to extend :** We conjecture that increased realism in more recent and powerful diffusion models has reduced the sensitivity difference. Thus the loss landscape of fake images should converge to that of the real images. You can investigate if this is indeed the case. This conjecture has important consequences: If true, images would become increasingly harder to detect. But if false, synthetic images look more realistic but carry the same artifacts that tell them apart from real images. Therefore, you will get data sets from more and less modern diffusion models and compare their loss-landscapes. A follow-up is to see when the conjecture is true, if more powerful foundation models restore the difference in the loss landscape. Self-proposed extensions are also appreciated.


## Topic 4: RL
- **Supervisor** : Hortence Nana
  
- **PAPER 4.1** : Bandit Learning in Many-to-One Matching Market
  
  - 👨‍🏫: ⭐⭐
  - 🖥️: ⭐⭐
  
  - **Brief description** : The paper considers a matching markets (like students to schools , doctors to hospitals or workers to     companies) where there are many agents and fewer arms (schools/companies), and each arm can take multiple agents (capacity). Agents learn over time which arms they like because rewards are uncertain or unknown. So it's multi-armed bandits, but with matching and stability rules.
  
  - **Link** : [https://openreview.net/pdf?id=rLuT4vG7NsO]
  
  - **How to reproduce** : Student should reproduce the centralized many-to-one bandit matching algorithms and results as provided in the paper. Authors implemented and test the centralized and decentralized Explore-Then-Commit and UCB alrorithms. Student will only focus on centralized part by implementing both or just focus on one of those algorithm if there isn't enough time.

  - **How to extend** : Student should focus on extending the original setting by changing the assumption on preferences. Specifically, in the extension, arm preferences are no longer given but must be learned from observed rewards, while agent preferences are known and fixed. This changes the learning objective: the learner now needs to estimate each arm's utilities for the available agents based on observed rewards over time. It makes the problem more complicated as each arm can content one or more agents. Focus on one algorithm and no need to design a new algorithm; instead, adapt the paper's algorithm to handle the new preference assumption and proof your theoretical result (regret bound).


    
- **PAPER 4.2** : Tight Regret Bounds for Stochastic Combinatorial Semi-Bandits

  - 👨‍🏫: ⭐
  - 🖥️: ⭐⭐⭐

  - **Brief description**: The paper studies an online learning setting called stochastic combinatorial semi-bandits. In this setting, a learning agent repeatedly selects subsets of items (subject to combinatorial constraints), observes their individual stochastic rewards, and aims to maximize cumulative reward over time. The key contribution of the paper is an analysis of the CombUCB1 algorithm, a UCB-like algorithm for this setting, and the derivation of tight regret bounds that are both gap-dependent and gap-free.
 
  - **Link** : [https://proceedings.mlr.press/v38/kveton15.pdf]
  
  - **How to reproduce**: Student should implement the CombUCB1 . concretely, carefully read and understand the problem definition (Section 2), the CombUCB1 algorithm and its initialization, and the theoretical results and proofs for regret bounds. Implement CombUCB1 as described in Algorithm 1 and make some experiments.
    
  - **How to extend**: As extention, student will just find a simple use case application and apply it there.
   
  
**NB**: For both papers, students will receive a pdf with a more formal description of each paper and tasks, as well as some link that will help to understand some concept.



## Topic 5: GenAI (Sampling in graph synthesizers)
- **Supervisor:** Abele Malan

- **General description:**
  Investigate the sampling procedure of iterative denoising (e.g., diffusion) deep learning models for generating synthetic graph data.
  Such data encompasses the graph structure and, potentially, auxiliary information (e.g., molecular atom and bond types).
  The reproducibility tasks focus on either exploring the sampling capabilities of a state-of-the-art model or techniques for conditioning sampling based on desirable properties across multiple models.
  Consequently, extensions tackle areas like generation speed/quality improvements or further increasing the complexity of targeted conditions.
  Since the work mainly concerns sampling, the longer and more resource-intensive part of training denoising models is not generally required.
  However, experiments involving new datasets or smaller auxiliary models could be an exception.

- **Paper 5.1:** DeFoG: Discrete Flow Matching for Graph Generation
  - **Link:**
    [https://openreview.net/pdf?id=KPRIwWhqAZ](https://openreview.net/pdf?id=KPRIwWhqAZ)
  - **How to reproduce:**
    Use the provided codebase (and model checkpoints) to run the DeFoG model proposed in the paper (without the other baseline models).
    Specifically, recreate Table 1 (with 10% and 100% steps), Figure 2 (a), and all Figure 3 subfigures.
  - **How to extend:**
    Investigate at least one of the points below.
    Self-proposed options are also welcome to be discussed.
    - additional sample distortion functions, with the target of further boosting generation quality (MMD or validity), for (specific) test scenarios;
    - graph editing (e.g., given a graph, use the model trained on planar data to edit it into a planar version) or augmentation (e.g., given a graph structure, add the node types) instead of generation from scratch;
    - dynamic optimization of sampling parameters (distortion, target guidance, stochasticity) during generation.


- **Paper 5.2:** Diffuse, Sample, Project: Plug-And-Play Controllable Graph Generation
  - **Link:**
    [https://openreview.net/pdf?id=ia0Z8d1DbY](https://openreview.net/pdf?id=ia0Z8d1DbY)
  - **How to reproduce:**
    Use the codebase provided by the PRODIGY framework authors and checkpoints from the authors of the underlying tested models to replicate PRODIGY's main results.
    Specifically, recreate Table 5 (only the entries with PRODIGY and without the EDP-GNN model), Table 10 (which is Table 6, with additional hyperparameter information), and Table 11 (which is Table 7 with more hyperparameter information; only the QM9 dataset and again without the EDP-GNN model).
    Note that the model referred to as DruM by PRODIGY authors has since been renamed to GruM by its authors.
  - **How to extend:**
    Investigate at least one of the points below.
    Self-proposed options are also welcome to be discussed.
    - optimizing for more than one condition at once (the method supports such a use case, but the paper does not test it);
    - additional constraint types (e.g., control the count of other graphlets, like squares instead of triangles);
    - new partial step $\gamma_t$ formulations (possibly based on an auxiliary neural network).

*Bonus extension:* Harness classifier-free guidance in DeFoG's classifier-free guidance to dynamically steer graphs towards the closest counterpart satisfying one of the hard constraints covered in PRODIGY and analyze the obtained performance.

## Topic 6 : RL (Zero-Sum Games, Multi-Armed Bandits and Differential Privacy)

- **Supervisor:** Elif

- **General description:**  
  This topic covers the intersection of zero-sum games, multi-armed bandits and differential privacy. The multi-armed bandit framework addresses the core challenge of balancing exploration and exploitation. In contrast, zero-sum games capture adversarial strategic interactions in which one player’s gain directly corresponds to the other’s loss. The connection between these two areas becomes especially interesting when the payoff matrix is unknown and must be learned through bandit feedback from the players' chosen actions. Differential privacy, as a way to formalize the amount of information about the output of an algorithm, adds another layer to this setting by ensuring that the information through bandit feedback does not compromise sensitive data about players' actions or rewards. 


- **Paper 6.1**
  - **Link:** [Matrix Games with Bandit Feedback](https://proceedings.mlr.press/v161/o-donoghue21a/o-donoghue21a.pdf)
  - **How to reproduce:**
    Students should begin by implementing the algorithms proposed in the paper and then simulate and evaluate the performance of the algorithms by generating regret plots over time (Section 5). These plots will help them to present how the algorithms learn strategies compared to the theoretical guarantees.
  - **How to extend:**
    While the paper focuses on zero-sum games, one natural extension is to explore general-sum games experimentally, in order to investigate whether similar regret behaviors or convergence properties can be observed beyond the adversarial setting. Another possible direction is to study alternative feedback approaches, for example, full-bandit feedback, where players observe the entire payoff matrix after each round. Comparing these scenarios can provide valuable insights into how the feedback structures affects learning dynamics and player’s strategies.

- **Paper 6.2**
  - **Link:** [Algorithms for Differentially Private Multi-Armed Bandits](https://arxiv.org/pdf/1511.08681) 
  - **How to reproduce:**
    This paper proposes a differentially private version of UCB in stochastic multi-armed bandit setting. To reproduce the results, students should implement the private UCB algorithm, then run simulations. Regret curves should be compared against the standard UCB and its private variants (section 4) and thus the regret bound should be verified.
  - **How to extend:**
    Students can implement other multi-armed bandit algorithms such as ETC, UCB and EXP3 to better understand baseline methods and compare them with the private UCB. One direction is to evaluate its performance in larger action spaces and then compare the results. Another interesting extension is to apply the differential privacy notions to zero-sum games.


