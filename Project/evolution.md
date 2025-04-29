---
marp: true
theme: default
paginate: true
class: lead
backgroundColor: #fff
footer: "**RWRL25:** *Interactions Between Learning and Evolution*"
---

# Interactions Between Learning and Evolution
--- *How Can Evolutionary Theory Explain Reinforcement Learning?*
## Tony Wang, 2025-04-28
### David Ackley & Michael Littman

- Weakly supervised learning.
- Can learning occur with only natural selection as feedback?
- Evolutionary Reinforcement Learning (ERL) algorithm.
- Learning + Evolution is most successful strategy, how could we use this to study Robot Learning?

---

# The Problem: Multiple Scales of Adaptation

- Life involves changes across scales — biochemical to population.
- Choosing a scale limits the model's assumptions.
- Need for multi-scale models.
- Focus: Interaction between **individuals** (learning) and **populations** (evolution).
- Challenge: Learning benefits from long lives, evolution from rapid generations.

---

# The Approach: Artificial Life & ERL

- Artificial Life (AL): Simulated environment for study.
- **Evolutionary Reinforcement Learning (ERL)**:
  - Combines genetic evolution and neural network learning.
- Enables substantial learning within short real-time generations.
- AL simulates moment-to-moment organism lifetimes.

---

# ERL Overview

- Natural selection provides minimal feedback: survival only.
- **ERL's solution**:
  - **Action Network**: Behaviors (modifiable via learning).
  - **Evaluation Network**: Goals (fixed, inherited).
- Inherited evaluation network guides learning during lifetime.
- Genetic code unchanged by learning; passed to offspring.

---

# World AL Setup

- 2D 100x100 grid world.
- Entities: ERL agents, carnivores, plants, trees, walls.
- Agents:
  - Inputs: Visuals, proprioception (energy, health).
  - Outputs: Move direction.
- Survival: Eat plants, dead entities, reproduce with energy.
- Carnivores: Attack agents, reproduce by feeding.

---

# Comparative Study Results

- Tested 5 strategies:
  - **ERL** (evolution + learning)
  - **E** (evolution only)
  - **L** (learning only)
  - **F** (fixed random actions)
  - **B** (Brownian motion)
- **Findings**:
  - Learning (ERL, L) boosts early survival.
  - Long-term: ERL outperforms L.
  - Evolution alone struggled.

---

# Why Evolution Alone Struggles

- Random action networks → early death → low genetic diversity.
- Hard to evolve behaviors from scratch.
- Easier to evolve **good goals** than **good behaviors**.
- Learning "fills in" details from high-level goals.

---

# Longitudinal Study: The Long Run

- Extended ERL population to ~9 million steps.
- Observations:
  - Large fluctuations in population sizes.
  - Eventual extinction.
- Aim: Analyze how learning and evolution contributed over time.

---

# Mutation Rates and Functional Constraints

- Used genetic mutation analysis:
  - Non-coding genes mutate faster → less functional constraint.
  - Plant-related genes mutated slower → more crucial for survival.
- Early: Learning critical (plant evaluation genes stable).
- Later: Inherited behaviors (action genes) dominate.

---

# The Baldwin Effect

- Learned behaviors ("plants are good") became instinctive.
- No Lamarckian inheritance: purely Darwinian via **Baldwin Effect**.
- Evolution internalized behaviors originally acquired via learning.

---

# Shielding and Goal Regression

- Agents later **liked** carnivores → maladaptation.
- **Shielding**:
  - Strong innate actions shield maladapted evaluation genes.
- **Goal Regression**:
  - Adaptive goals deteriorate once behaviors are instinctive.

---

# Discussion: Interaction Effects

- **Baldwin Effect**:
  - Learning behaviors → later inherited.
- **Shielding**:
  - Innate behaviors reduce selective pressure on goals.
- **Goal Regression**:
  - Successful goals deteriorate once "solved too well."
- Phenomena challenge views on species-level intelligence.

---

# Conclusion

- Learning and evolution interact in complex ways:
  - Baldwin Effect explains early adaptation success.
  - Shielding explains long-term instability and extinction.
- Artificial life simulations reveal multi-scale evolutionary dynamics.
- Future: Shielding may allow discovery of new adaptive strategies (e.g., agriculture).

---

# References

- Ackley, D., & Littman, M. (1991). Interactions Between Learning and Evolution. Cognitive Science Research Group, Bellcore, 445 South Street, Morristown, NJ 07960.
- Baldwin, J. M. (1896). The Evolution of Animal Intelligence.
- Hinton, G. E., & Nowlan, S. J. (1987). How Learning Can Guide Evolutionary Processes.
- Littman, M. L. (1994). Learning and Evolution. MIT Press.

---
