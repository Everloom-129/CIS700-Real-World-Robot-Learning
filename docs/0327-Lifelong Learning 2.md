# Lifelong Learning II

Tony Wang

03/27/2025





## Continual Learning Meets Bias Correction in Deep RL: A Look at Progressive Neural Networks and the Primacy Bias

In the landscape of deep reinforcement learning (RL), two persistent challenges continue to shape research:  
1. **Catastrophic forgetting** when transferring across tasks, and  
2. **Primacy bias**, where agents overweight early experiences at the cost of newer, possibly more informative data.

In this blog, I’ll dive into two seminal papers that address these problems from different angles:
- [**Progressive Neural Networks** (Rusu et al., 2016)](https://arxiv.org/abs/1606.04671)
- [**The Primacy Bias in Deep Reinforcement Learning** (Nikishin et al., 2022)](https://proceedings.mlr.press/v162/nikishin22a/nikishin22a.pdf)

Let’s walk through the core ideas, architectural designs, and broader implications of each paper, and then talk about how these might be combined—or at least co-exist—to push the boundaries of generalizable agents.

---

## Paper 1: Progressive Neural Networks (PNNs) – Tackling Catastrophic Forgetting

One of the fundamental challenges in lifelong learning is that when a neural network learns a new task, it often **overwrites** the weights used for previous tasks. Fine-tuning on a new task leads to "forgetting" the old one.

PNNs propose a simple but powerful architectural trick:  
- **Freeze** the parameters of previously learned tasks.  
- **Add** a new column (a full neural net) for each new task.  
- **Connect** new columns to older ones via **lateral connections**, allowing information flow without weight overwriting.

So instead of trying to cram new and old knowledge into the same network, PNNs compartmentalize learning and **encourage feature reuse** through lateral connections.

**Empirical Results:**  
They evaluate PNNs on a suite of Atari games and 3D navigation tasks, and the results are solid:  
- Better performance than pretraining + fine-tuning.  
- Strong transfer, particularly when earlier tasks share useful structure.  
- Clear avoidance of catastrophic forgetting.

**Critical Takeaway:**  
PNNs are a strong choice for **lifelong, multi-task reinforcement learning**, though the cost is architectural growth with each new task. There's a clear trade-off between **scalability** and **preservation of knowledge**.

---

## Paper 2: Primacy Bias – When Your Agent Gets Stuck in the Past

Nikishin et al. ask a different but equally foundational question:  
> What if the agent's problem isn’t forgetting—but the opposite? What if it remembers **too much of the wrong stuff**, especially from the beginning?

They observe that standard deep RL agents (e.g., DQN) **overfit to early experiences** in training. This is the **primacy bias**. Since experience replay doesn’t reweight old vs. new transitions, and the network’s initial weights get reinforced through bootstrapping, agents tend to stick to their first impressions.

**Proposed Fix:** Periodically **reset the last layers** of the network during training, while keeping the replay buffer intact.

This gives the agent a chance to:
- Reinterpret the same data with a new perspective.
- Avoid overly anchoring to early trajectories.
- Discover better policies that might have been suppressed by initial overgeneralization.

**Evaluation:**  
- On both **Atari 100k** and **DeepMind Control Suite**, reset-based agents consistently outperform baselines.  
- Surprisingly effective despite its simplicity—no need to change the replay buffer, loss function, or architecture.

**Broader Insight:**  
This paper reframes exploration and generalization as not just **external data problems**, but also **internal inductive bias problems** of deep networks.

---

## How These Ideas Could Coexist

Both papers push RL in the direction of more stable and generalizable agents—but from opposite sides:

| Problem        | PNNs                          | Primacy Bias Paper              |
|----------------|-------------------------------|----------------------------------|
| Forgetting     | Solve by freezing & expanding | Not addressed                    |
| Overfitting to early data | Not addressed                | Solve by resetting last layers   |
| Transfer       | Enabled via lateral connections | Orthogonal to transfer          |

If we’re building a real-world multi-task robotic agent (say, in a kitchen or factory), we might want:
- The **stability and modularity** of PNNs,
- Combined with **periodic resetting** to allow fresh policy discovery even within a single task.

Imagine a PNN that resets its newest column’s final layers every so often—this could allow **stable accumulation** of skill across tasks, while still adapting flexibly within each one.

---

## Closing Thoughts

These two papers taught me to respect the **temporal dynamics of learning itself**. Not just *what* the agent sees, but *when* and *how* it learns from it—matters deeply. In practical deployments, especially with robotic agents operating in long-horizon or evolving environments, both forgetting and overfitting can quietly kill performance.

Solutions like PNNs and reset policies remind us that learning systems need **architecture-aware** and **training-aware** mechanisms to achieve robustness. And perhaps more importantly, they show how small tweaks—like freezing or resetting—can shift the learning trajectory in big ways.

---
