# Robot Perception 1: ***A Critique of Pure Vision***

Tony Wang

02/02/2025

> 纯粹视觉批判
>
> Patricia S. Churchland, V. S. Ramachandran, and Terrence J. Sejnowski

![image-20250204113454911](./0204-Robot%20Perception%201.assets/image-20250204113454911.png)





In 1994, the the cretaceous period of computer vision, the academic world was largely influenced by the "Theory of Pure Vision". This theory, which the authors refer to as an "orthodoxy," points that the goal of vision is to create a detailed internal replica of the visual world. This can be achieved through hierarchical processing and operating independently of other senses or actions. However, the authors propose a series of argument against which much computer vision research was being conducted at the time.



------

### The Rise and Fall of "Pure Vision"

In 1994, during the Cretaceous period of computer vision, academia was largely shaped by the "Theory of Pure Vision." This theory, described by the authors as an "orthodoxy," suggested that the purpose of vision was to create a detailed internal representation of the world, primarily through hierarchical processing, and independent of other sensory modalities or motor functions. However, these has been challenged by Authors with a series of arguments:

#### The Pillars of "Pure Vision"

- **Hierarchical Processing:** Vision was believed to progress through a strict hierarchy, from the retina to the LGN to the visual cortex, with each layer extracting more abstract features until a complete internal representation of the scene was formed.
- **Scene Recovery:** Researchers sought to reconstruct 3D spatio-temporal representations from 2D inputs, assuming that a more accurate internal model meant better perception.

##### Issues raised by CV that time

- **Early Vision Problems:** Research emphasized low-level visual tasks like edge detection, stereo matching, and motion estimation as prerequisites for higher-level understanding.
- **Local Processing:** Early models, such as Ullman’s (1979) motion correspondence framework, relied heavily on localized, bottom-up information rather than global constraints.
- **Active Vision Emerges:** By the late 1980s, alternative perspectives, such as "active vision," gained traction, introducing the idea that perception is shaped by movement and interaction with the environment (Bajcsy, 1988; Ballard & Brooks, 1989).

While these foundational ideas dominates computer vision, the strict "pure vision" doctrine was not purely accurate anymore.

### Interactive Vision: new paradigm

From biology, psychology and philosphy, authors argue against the traditional hierarchical model. For example, **backprojections in the visual cortex**—where higher-order brain regions modulate early visual processing. In addition, research has shown that motion control directly affects vision, fundamentally challenging one-way, isolated visual processing assumptions.

#### Note: The Principles of Interactive Vision

1. **Vision for Action:** Perception evolved primarily for action, not just scene reconstruction.
2. **Partial Representation:** The brain does not construct a full, detailed world model; it extracts only task-relevant information.
3. **Predictive and Exploratory Vision:** Perception is inherently predictive, allowing organisms to anticipate events and adapt behavior accordingly.
4. **Multi-modal Integration:** Vision does not operate in isolation—it is intertwined with touch, audition, and proprioception.
5. **Learning and Memory:** Perception is shaped by prior experience and learning, making it inherently dynamic.
6. **Relevance Over Fidelity:** The brain prioritizes information relevant to survival and decision-making, rather than striving for perfect reconstruction.
7. **Feedback Loops:** Information flows bidirectionally, with higher cognitive functions influencing early sensory processing.

This paradigm shift—from a passive, reconstructive model to an **active, embodied, and predictive** one—was a fundamental rethinking of both biological and artificial vision systems. Interestingly, it is exactly what robotics fighting against till even now. 

------

### Implications: Modern Robot Perception

The robotics is always closely connected with computer vision. Even in 2025, modern AI and robotics research continues  similar issues, varying in new forms. The rise of **end2end deep learning** has replaced traditional hand-crafted feature extraction. But as discussed in Canvas: https://canvas.upenn.edu/courses/1843097/discussion_topics/9979345, we still unknow how to integrate **multi-modal perception, predictive modeling, and active control.**



- **The Multi-modal Data Challenge:** As stated in CIS5800, Many robotics applications attempt to fuse vision with tactile and auditory signals, but current approaches often rely on **hand-designed heuristics**, limiting their adaptability.
- **Data Scale Matters:** Just as early "pure vision" struggled with limited data, today’s multi-modal systems require vast, diverse datasets. Autonomous driving, for instance, has explored RGB-LiDAR-radar fusion, yet Tesla’s Full Self-Driving (FSD) system has controversially abandoned non-visual sensors in favor of **pure RGB models** trained on massive-scale data.
- **Embodied AI and Vision-Language Models (VLMs):** Cutting-edge research in **VLMs for robotics** suggests that integrating language with vision may help bridge perception and action. Projects like **ReKep and ECoT** aim to ground vision in reasoning via language, mirroring some of the principles advocated in the 1994 critique.
- **Predictive Perception:** The interactive vision framework emphasized that perception is predictive rather than reconstructive. Modern robotics increasingly embraces **world models** and **latent-space planning**, suggesting that vision should guide future actions rather than merely capture past observations.

### A Continuing Evolution

The 1994 critique of "pure vision" was a watershed moment, but its insights remain highly relevant today. Just as the early 90s saw a shift from **static, hierarchical perception** to **interactive, embodied vision**, modern AI is undergoing a transformation—from **static, supervised learning** toward **real-time, action-driven learning**. Future advances in **multi-modal learning, predictive modeling, and vision-language integration** may continue to shape the next era of robot perception.

In essence, the lesson remains: vision is not an isolated process but a deeply **integrated, active, and goal-driven function**—one that extends far beyond pixels and into the very heart of intelligent behavior.





## Archaeologist



their 1994 paper, "A Critique of Pure Vision," Patricia S. Churchland, V.S. Ramachandran, and Terrence J. Sejnowski challenge the traditional view that the visual system operates independently to create a detailed internal representation of the external world.  propose that vision is deeply interconnected with other sensory modalities, motor planning, and prior knowledge, suggesting an interactive model of perception. ([triciachurchland.co(https://patriciachurchland.com/wpontent/uploads/2020/05/1994-Critique-Pure-Vision.pdf?utm_source=chatgpt.com))

**Influential Preceding Work:**

An earlier work that significantly influenced this paper is David Marr's "on: A Computational Investigation into the Human Representation and Processing of Visual Information" (1982). Marr's framework, which emphasizes a hierarchical and modular approach to visual processing, serves as a foundational reence point that Churchlanand colleagues critique and build upon in their discussion of interactive vision.

**Subsequent Impact:**

A notable work thates "A Critique of Pure Vision" is the 1997 paper titled "A Critique of Pure Audition" by Malcolm Slaney. In this paper, Slaney extends the discussion to the auditory domain, examining whether auditory perception also involves significant top-down processing and interactive elements, thereby badening the implicatnof Churchland et al.'s critique beyond vision to sensory processing in general. ([engineering.purdue.edu](https://engineering.purdue.edu/~malcolm/interval/1997-056/PureAudition.pdf?utm_source=chatgptm))

In summary, "A Critique of Pure Vision" serves as a pivotal work that challenges traditional models of sensory processing, advocating for a more integrated and interactive understanding of perception.

![image-20250204113533309](./0204-Robot%20Perception%201.assets/image-20250204113533309.png)



![image-20250204113541531](./0204-Robot%20Perception%201.assets/image-20250204113541531.png)