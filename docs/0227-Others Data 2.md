# Learning from Others' Data II

Tony Wang

02/27/2025





> **X-Embodiment:**  **"Pushing the Limits of Cross-Embodiment Learning for Manipulation and Navigation"**
>
> **"SFV: Reinforcement Learning of Physical Skills from Videos"**.  

---

# **Teaching Robots Across Bodies and Screens: Can We Learn Everything from Data?**  

If robots are ever going to truly understand the world, they need to learn like we do—by watching, experimenting, and transferring skills across different situations. Two recent papers push the boundaries of how robots can **generalize knowledge across embodiments** and **learn physical skills from video**. One asks: *Can a single model control vastly different robots—arms, drones, quadrupeds—by finding commonalities in their motion?* The other asks: *Can we skip expensive motion capture and teach robots directly from online videos?*  

### **The Dream of Generalist Robots (X-Embodiment Learning)**  

One of the biggest roadblocks in robotics is that most models are **hyper-specialized**—a robotic arm trained to stack blocks won’t suddenly know how to navigate a hallway. But humans don’t work that way. We use **shared sensorimotor principles** across different tasks.  

The **X-Embodiment** paper explores this by training a **single goal-conditioned policy** across 18 datasets spanning robotic manipulation, navigation, and even driving. The key idea? **Motion, whether it’s a robotic arm reaching for a cup or a wheeled robot moving toward a waypoint, follows similar geometric constraints.** By aligning action coordinate frames across embodiments, they show that co-training improves both manipulation and navigation:  
- **Adding navigation data improved robotic manipulation success by 20%.**  
- **Adding manipulation data improved navigation by 5-7%.**  
- **The model could control entirely new robots zero-shot.**  

This reinforces the idea that robots can **share structured knowledge across bodies**, even when their action spaces look completely different.  

But does this mean we can train a single model to control all robots? Probably not yet. The policy still **struggles with embodiment-specific constraints**—manipulators are limited by joint angles, wheeled robots can’t move vertically. While the paper proves that large-scale cross-embodiment learning is possible, the next challenge is ensuring **fine-grained control without losing generalization**.  

### **Can Robots Learn to Move by Watching YouTube? (SFV: Skills from Videos)**  

Imagine if a humanoid robot could learn parkour just by watching viral clips of free runners. That’s the promise of **SFV (Skills from Videos)**—a system that combines **pose estimation from videos with reinforcement learning** to teach simulated robots to perform dynamic skills.  

The pipeline works like this:  
1. **Extract 3D motion data from monocular video** using deep pose estimation.  
2. **Reconstruct missing frames and refine motion** to create smooth trajectories.  
3. **Train a physics-based controller** via reinforcement learning to imitate the motion in simulation.  

What’s impressive is that **this method enables robots to learn highly dynamic behaviors like flips, cartwheels, and martial arts—without any motion capture data.** Since traditional motion capture is expensive and limited, this unlocks **a massive dataset of real-world demonstrations** from online videos.  

But here’s the catch:  
- **Pose estimation errors accumulate**, leading to unnatural or unstable motions.  
- **Physics-based controllers don’t always adapt well to new morphologies**, meaning a skill learned for one robot might not transfer to another.  
- **Real-world deployment is still a huge challenge**—learning to backflip in simulation is very different from executing it on an actual humanoid.  

### **Where Do We Go from Here?**  

Both of these papers hint at a future where robots learn **more like humans**—not just from carefully curated datasets, but by **watching, reasoning, and generalizing**. But there’s still a gap between data-driven learning and true **embodied intelligence**.  



At the end of the day, the real question is: *How do we balance generalization and specialization?* Can we build a **single robot policy that adapts to any task**, or do we always need some level of fine-tuning? The answer might be **somewhere in the middle**—a generalist foundation model that **learns core sensorimotor principles**, with task-specific refinement for high-precision control.  

Either way, the future of robot learning isn’t just about bigger datasets. It’s about **smarter, more structured representations of the world.**  







----

## Course note

Only Antonio today. No prelec



### SFV: how to generate natural action?

-> how to align with learning data?

-> how to realize generalist robot?





Antonio is optimistic about this direction. 

https://hgaurav2k.github.io/hop/, HOP with people hand pose & learn from its trajectory

- however, human in the video can be very noisy, in the air or even in the hand
- but it is one way to scale up robot learning



ASI's challenge

- hyperparameter tuning
- curriculum is unclear, eg: OPENAI's play & hide + football game

#### good idea: use VLMs to generate feedback & auto curriculum for the task

using video to generate keypoints for RL is still very hot today









### Xembodiment

Question: model arch?

Question: any reproduction ? is that work?

- seems less, most on nav part





navigation dataset could benefit the manipulation task 

- the recording is longer with more context annotation, not just simple pick and place
- only manipulation vs co train: 30% + on acc







how 







#### following works

1. crossformer 2024 : scaling x-embodiemnt



co-training improves performance for ALOHA and TELLO(unseen in training data)

![image-20250227111816759](./0227-Others%20Data%202.assets/image-20250227111816759.png)



2. Kaiming's Heterogenous Pretrained transformers

- not opensourced
- "***you should not trust too much about your isaacsim simulator --- antonio***"

- pretrained represenation model with finetuning outperform policies trained from scratch in the real world. but does not outperform generalist polices in simulation





#### archelogist 

1. RoboNet from Kostas group 

   https://www.analyticsinsight.net/latest-news/researchers-developed-robonet-easy-capture-diverse-datamore 

2. more i forgot..





certain finetuning may be necessary for cross embodiment training





Debate on Generalist policy, pi0 and Helix...



robotists should always find failure & limitations





