# The Development Perspective on Robot Learning II: **Sensorimotor Learning & Intrinsic Motivation**

Tony Wang

02/13/2025





## Revisiting the Foundations of Autonomous Learning and Motor Control

Nowadays, robotics is growing faster than ever before, it's crucial to revisit foundational research that continues to shape our understanding of how machines learn and interact with the world. Antonio provides paper written years apart, while offering insights that remain remarkably relevant to the SOTA research we have today. These are "Principles of sensorimotor learning" (2011) and "Intrinsic Motivation Systems for Autonomous Mental Development" (2007). Let’s dive in.

### "Optimal Sensorimotor Control" - Understanding How We Move

Published in 2011, this paper offers a comprehensive overview of the computational principles underlying human motor control and learning. It explores how our brains handle the complexities of movement, focusing on optimality, internal models, and the learning processes involved.

- **Key Concepts:**
  - **Optimal Control:** This framework suggests that our motor system strives to minimize some cost function (e.g. energy expenditure or movement variability) under given constraints. In other words, we move in the most efficient way possible given the task at hand.
  - **Internal Models:** These are neural simulators that predict the sensory consequences of our actions. They allow us to make feedforward (predictive) movements as well as adapt our movements based on sensory feedback. The brain utilizes an **efference copy** of the motor command in order to predict the sensory consequences of an action. Forward models, which predict the sensory consequences of action, are used in conjunction with this efference copy.
  - **Bayesian Inference:** This mathematical framework helps us to combine different sources of information in an optimal way, which includes sensory inputs (e.g. visual and tactile information) and internal models to refine our estimates of the environment. A Kalman filter is a kind of estimator that uses Bayesian inference to estimate the state of the world, taking into account sensory feedback and internal models.
  - **Learning Processes:** Motor learning can be distinguished by the type of information used as a learning signal. The paper identifies error-based learning, which uses the difference between predicted and actual outcomes, use-dependent learning, which changes the motor system through repeated movements, and reinforcement learning, which uses information about the relative success or failure of a movement.
  - **Motor Primitives:** The paper also discusses the idea that movements are built from basic building blocks of neural control called motor primitives, which can be combined in many different ways to produce a range of behaviors.
  - **Credit Assignment:** This process of attributing errors to their underlying causes both spatially and temporally is critical for effective learning. Contextual credit assignment attributes errors to specific contexts, such as a grasped object, and temporal credit assignment handles errors that occur over different timescales. The paper also discusses how these assignments can be affected by prior experience.
  - **Dual Rate Learning:** The concept of fast and slow learning processes that act on different timescales is introduced. The fast learning process can learn quickly but does not retain information well, while the slow process learns more slowly but retains information over a longer time.
- **Relevance Today:** The principles outlined in this paper have been highly influential in robotics. However, current robots still lag far behind human performance in many ways. The idea of using internal models for prediction and control, and of optimizing motor behavior based on a cost function, is foundational in robotics research. However, as the paper points out, challenges remain in transferring this knowledge to complex, real-world tasks. There is also the question of how to integrate these insights with a system like IAC, to allow for a robot that can not only plan and execute movements effectively but also seek out new challenges to further its development.
- **Personal Thought:** What I find most compelling about this paper is its deep dive into the mechanisms of how humans adapt their movements. The notion that our brains are constantly optimizing our actions, often without our conscious awareness, is powerful. It's fascinating to consider how we can translate these principles into more adaptable and intelligent robots. Also the idea of multiple timescales of learning is a concept that wasn't discussed much in the 2007 paper, but is a key component of the 2011 paper. How can an intrinsic motivation system make use of these fast and slow timescales of learning for accelerated learning and adaptation?

### "Intrinsic Motivation Systems for Autonomous Mental Development" - A Robot's Drive to Learn

This paper explores a fascinating question: can we give robots the intrinsic motivation to explore and learn like children do? The authors propose the concept of **Intelligent Adaptive Curiosity (IAC)**, an intrinsic motivation system that pushes a robot towards situations where it can maximize its learning progress.

- **The Core Idea:** IAC is designed to drive a robot towards situations that are neither too predictable nor too unpredictable. This allows the robot to focus on areas where learning is most fruitful. It's like a child who is more drawn to a toy they can almost understand but not completely, avoiding both the too-familiar and the utterly baffling.
- **How it Works:** The system uses a combination of learning machines and meta-learning machines. A learning machine (M) predicts the consequences of the robot’s actions in a given context. A meta-learning machine (metaM) predicts the errors M makes. A knowledge gain assessor (KGA) is then used to evaluate the learning progress by tracking the difference between expected and recent error rates. This leads the robot to actively seek situations where the error rate is decreasing, indicating that it's learning.
- **Autonomous Development:** A key feature of IAC is its ability to drive autonomous development. The robot’s activities increase in complexity as it learns, and developmental sequences self-organize without human supervision. In experiments, robots using IAC moved from easy-to-learn situations to increasingly difficult ones, avoiding areas where they couldn't learn anything. The system also categorizes situations, splitting the sensorimotor space into different regions which correspond to different kinds of activities.
- **Relevance Today:** While this paper is from 2007, its core idea is more relevant than ever. Today, we have deep reinforcement learning, which wasn't very mature when this paper was written. We have the potential to greatly improve on the simple learning mechanisms in IAC using, for example, neural networks, allowing for more sophisticated state representations and action selections. We also have unsupervised learning methods like contrastive learning and clustering, which could be used to generate more meaningful categorizations of sensorimotor experience than simple incremental space splitting. The paper mentions that a limitation of existing systems is that they have not been shown to allow for the autonomous formation of more than one stage of development. Can these more modern techniques overcome that limitation to create robots that can learn more complex, hierarchical behaviors?
- **Personal Thought:** I’m particularly struck by the emphasis on task-independent learning. The idea that a robot should be able to learn without specific, pre-programmed tasks is essential for achieving truly autonomous systems. IAC provides a framework for how this can be done, and it's exciting to think about what advanced learning methods could do if integrated with this intrinsic motivation system.

- 

### Combining Insights for the Future

Individually, these papers provide a strong foundation for the future of autonomous learning. Together, they point towards the possibility of creating robots that are not just tools, but intelligent, adaptable partners. The IAC system provides the motivation, and optimal control provides the means. The key is to find the best ways to integrate these approaches.

By combining the drive for learning with the ability to optimize movements, we can create robots that are not only curious and exploratory but also incredibly skilled. This is where the future of robotics is headed, and it’s exciting to be part of that journey.



> Another blog enhanced with ChatGPT-canvas is [here](https://chatgpt.com/canvas/shared/67ad6a63bf7881918ebd2e536101dc04) 
