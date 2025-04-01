# Robot Design

Tony Wang

04/01/2025




## 🧠 **Reading Blog – Apr 1: Robot Design ≠ Just Picking Parts**

**TL;DR**  
Two very different but super complementary reads this week:  
1. Censi's *“Mathematical Theory of Co-Design”* — abstract but v. foundational  
2. Kim et al.’s LEONARDO robot — bird-like, flying-legged hybrid that skates + slacklines

---

### 📘 1. **Co-Design as Optimization over Constraints Graphs**

Censi drops a heavy-duty formalism for thinking about **robot design as a structured optimization problem**, not just “pick sensor, pick motor, hope for best.”  

Core idea: a “design problem” is a tuple —  
- **F** (functionality space)  
- **R** (resources space)  
- **I** (implementations)  
w/ maps `exec(i)` → F, `eval(i)` → R

You're looking for minimal R that satisfies F — i.e., find the **Pareto front**, not just best scalar. These get composed into **co-design problems**, incl. w/ feedback loops (e.g. heavier battery → more torque → bigger motor → … back to heavier battery 🤯).  

✨ *MCDPs* (Monotone Co-Design Problems) — if F and R are posets, and the maps are monotone + Scott continuous (CS people: think denotational semantics), then we can actually **solve** these using fixed-point theorems (Kleene ascent, etc.).

🧠 Think of this as the **category theory of robot design**. Very abstract, but gives you tools to reason about subsystem dependencies & recursive constraints rigorously.

---

### 🤖 2. **LEO: Flying-Legged Birdbot That Skates**

LEONARDO is basically a **lightweight biped strapped to quadrotor thrusters**, and it can:
- walk
- hover
- slackline (!!)
- ride a skateboard (!!)

It blends **terrestrial + aerial locomotion** w/ shared control: legs handle CoM, thrusters give stability (esp. for pitch/yaw). Uses **sync'd control of legs + props**, where each subsystem compensates for the other's limitations (e.g., legs = low inertia → agile, but props assist for ground stability).  

👟 Legs = carbon fiber, super light, actuated via 3 BLDC servos  
🌀 Props = 4 tilted-inward thrusters (25°) → better torque control  
🧠 Control stack = switches between walk/fly based on foot contact sensors

Also has this cool metric:  
**Integration mass ratio** = (mass for walk + fly subsystems) / total mass  
→ LEO = 1.39 → shows shared components across modes (i.e. not just bolt-on)

---

### 🔄 Design ↔ Learning

What ties the two papers together is the **idea that “design is part of the intelligence.”** LEONARDO's balance tricks aren't just about control—they're enabled by hardware choices that were clearly co-optimized.  

If we take Censi's framework seriously, we could imagine:
- Learning-based planners that operate *during* co-design (design as part of the learning loop)
- Learned policies that exploit system-specific Pareto optimalities  
- End-to-end sim-to-real that doesn't just adapt the policy, but iteratively tweaks design params too

---

### 💭 Questions I'm bringing to class:

- How practical is Censi's framework for real design pipelines? (Can we plug into CAD tools? URDFs?)  
- Could we use co-design as a regularizer for learning policies?  
- In LEONARDO, what decisions came from co-design vs. trial-and-error tuning?

---

Shout if anyone wants to go deeper on fixed points or poset math — I skimmed but happy to dive in.
