# Learning from Real-World Robot Data II: **Diffusion Policy, Aloha, Robots in Homes**

Jie Wang

02/20/2025

> **Diffusion Policy: Visuomotor Policy Learning via Action Diffusion .** 
> Cheng Chi∗1 , Zhenjia Xu∗1 , Siyuan Feng2 , Eric Cousineau2 , Yilun Du3 , Benjamin Burchfiel2 , Russ Tedrake 2,3, Shuran Song
> **On Bringing Robots Home** 
>
> Nur Muhammad (Mahi) Shafiullah∗† NYU Anant Rai∗ NYU Haritheja Etukuru NYU Yiqian Liu NYU Ishan Misra Meta Soumith Chintala Meta Lerrel Pinto NY



**Bringing Intelligent Robotics Home: The Future of Adaptive Robot Learning**

For decades, humans have dreamed of robots that seamlessly integrate into our daily lives. We looks for intelligent assistants can do household tasks as ease as a human. While robotic vacuum cleaners and dishwashers have become commonplace, the true vision of a generalist home robot, one that can learn, adapt, and assist with diverse real-world tasks, remains just out of reach. My long-term project is aimed at bridging this gap by developing a system that can quickly and effectively learn from human demonstrations, making intelligent home robots a reality. Here the two readings are especially helpful. 

### The Vision: Robots That Learn Like We Do

The core idea behind this project is simple yet transformative—why should robots require months of training and complex programming when humans can learn a new task in minutes? Instead of pre-programming every possible action, my approach leverages **imitation learning** and **diffusion-based policy models** to enable robots to learn from observation, adapting to new environments with minimal supervision.

**Dobb·E** is an innovative learning framework by Meta. They train robots to perform a variety of household tasks with just **five minutes of user demonstrations** and a short fine-tuning process. The key to making this possible is a low-cost but highly effective demonstration collection tool—**The Stick**, a simple reacher-grabber augmented with an iPhone. This tool enables seamless data collection, capturing RGB-D images, 6D motion, and high-fidelity pose information, all of which contribute to the training of our Home Pretrained Representations (HPR) model.

### The Technology: Diffusion Policies for Adaptability

Traditional robot learning methods struggle with **multimodal action distributions** and **real-time adaptability**. This is where **Diffusion Policy** models come in. Inspired by the success of **Denoising Diffusion Probabilistic Models (DDPMs)** in generative AI, DP approach refines noisy inputs into structured robot actions, allowing for:

- **Multimodal Action Learning** – The robot can generate and select from multiple viable action paths instead of being constrained to a single trajectory.
- **Temporal Consistency** – Unlike conventional models that predict actions frame-by-frame, diffusion policies generate entire action sequences, ensuring smooth and realistic motion.
- **Stable Training and Execution** – By learning a gradient-based energy function rather than direct policy mapping, the model achieves higher robustness and generalization across different tasks.

### Real-World Testing: Learning in Homes, Not Labs

One of the biggest limitations of current robotics research is that most models are trained in controlled lab settings. However, real homes present a **messy, unpredictable** environment filled with **shadows, clutter, and varying user preferences**. The [DOBB·E](https://dobb-e.com/#) tackles this challenge head-on by deploying our trained policies in **actual homes**, testing across diverse environments with varying lighting, objects, and user interactions.

After **30 days of real-world experiments in 10 different homes**, DOBBE system has successfully learned and executed over **100 household tasks**—including picking up objects, opening doors, and handling kitchen tools—with an impressive **81% success rate**. These results mark a significant step towards creating general-purpose household robots that can adapt and learn in **any real-world home**.

### The Road Ahead: Scaling Intelligent Home Robotics

While the progress so far has been exciting, roboticists are just getting started. The next steps involve:

- **Expanding the dataset**: Collecting more diverse demonstrations across different homes to improve generalization.
- **Enhancing real-time adaptability**: Incorporating reinforcement learning to allow robots to refine actions based on user feedback.
- **Integrating advanced sensory inputs**: Exploring multimodal learning with touch and audio sensors to improve interaction quality.

The dream of a truly **intelligent, adaptable home robot** is within reach. By combining **human-inspired learning**, **cutting-edge AI models**, and **real-world deployment**, we are paving the way for robots that don’t just execute commands—but truly understand and assist in our everyday lives.

The future of home robotics starts now. Let’s build it together.
