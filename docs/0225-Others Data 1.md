# Learning from Others' Data I: Visual Representations, What Works and What Doesn’t?

Tony Wang

02/25/2025

> 1. The Surprising Effectiveness of Representation Learning for Visual Imitation 
>
>    https://arxiv.org/pdf/2112.01511
>
> 2. An Unbiased Look at Datasets for Visuo-Motor Pre-Training
>
>    https://openreview.net/pdf?id=qVc7NWYTRZ6



In robot learning, visual representation learning has been a hot topic, especially in imitation learning and visuomotor control. Two recent papers—**"The Surprising Effectiveness of Representation Learning for Visual Imitation"** and **"An Unbiased Look at Datasets for Visuo-Motor Pre-Training"**—offer interesting perspectives on how well visual representations can transfer to robotic tasks. But do these methods truly generalize? Based on my own testing, I have some reservations.

## **What These Papers Say**

### **1. The Surprising Effectiveness of Representation Learning for Visual Imitation**

This paper argues that visual imitation learning struggles because it tries to solve two problems at once:

1. Learning a good **visual representation** from raw images.
2. Learning how to **map that representation to actions**.

To address this, the authors propose **decoupling representation learning from behavior learning**. They pre-train a vision encoder using **Bootstrap Your Own Latent (BYOL)** and then use a k-nearest neighbor (kNN) approach to predict actions during deployment. Their results suggest that **good representations alone can go a long way in enabling imitation**, even without end-to-end behavior cloning.

### **2. An Unbiased Look at Datasets for Visuo-Motor Pre-Training**

This paper explores how **dataset choice** impacts visuomotor pre-training. The authors compare several large-scale datasets—including **ImageNet, Ego4D, 100 Days of Hands, Kinetics, and RoboNet**—and evaluate their effectiveness in fine-tuning for robotic manipulation.

Key takeaways:

- **Traditional vision datasets (ImageNet, Kinetics, DoH) outperform robotics-specific datasets (Ego4D, RoboNet)**.
- **Scaling up dataset size doesn’t always help**—the way data is curated matters more than raw volume.
- **Combining diverse datasets can increase robustness, but only if balanced properly**.

This challenges the assumption that robotics-specific data is always better. Instead, broader **internet-scale datasets seem to provide stronger priors** for robot learning.

## **My Thoughts: Generalization, Object-Centric Representations, and Real-World Testing**

In my test on PI0-FAST, it seems the 3B vlm encoder can handle complex vision input easily, the vision prior will not be affected by background change.

### **A More Structured Approach: Object-Centric Representations**

Instead of relying purely on end-to-end visual pre-training, **object-centric representations** might provide a more structured way to improve generalization. Papers like **POCR** and **HODOR** propose breaking down scenes into meaningful object representations, making it easier to generalize across different environments. This is especially relevant for **multi-step tasks**, where pure pixel-based representations often struggle.

### **Future Directions: Embodied Chain of Thought** & VLA

Another promising direction is **Embodied Chain of Thought (e-CoT)**, which integrates reasoning into visuomotor learning. Instead of treating imitation as a direct mapping from pixels to actions, e-CoT introduces **hierarchical reasoning**, helping robots understand task structure rather than just replicating motions.

## **Final Thoughts**

Both papers provide valuable insights, but I believe **future progress will come from integrating structured representations, task priors, and reasoning-based approaches**. Instead of simply scaling up datasets or tweaking pre-training methods, we should explore **how robots can break down and reason about their environments**—something object-centric learning and hierarchical reasoning models like e-CoT are starting to tackle.

Would love to hear thoughts from others—should we continue refining visual representation learning, or is it time to rethink the entire approach?
