# Learning from Internet Data I

Tony Wang

03/04/2025



> **Robot Learning Manipulation Action Plans by “Watching” Unconstrained Videos from the World Wide Web** 
>
> Yezhou Yang University of Maryland yzyang@cs.umd.edu Yi Li NICTA, Australia yi.li@nicta.com.au Cornelia Fermuller ¨ University of Maryland fer@umiacs.umd.edu Yiannis Aloimonos University of Maryland yiannis@cs.umd.edu

> **Do As I Can, Not As I Say: Grounding Language in Robotic Affordances** 
>
> 1 Michael Ahn∗ , Anthony Brohan∗ , Noah Brown∗ , Yevgen Chebotar∗ , Omar Cortes∗ , Byron David∗ , Chelsea Finn∗ , Chuyuan Fu† , Keerthana Gopalakrishnan∗ , Karol Hausman∗ , Alex Herzog† , Daniel Ho† , Jasmine Hsu∗ , Julian Ibarz∗ , Brian Ichter∗ , Alex Irpan∗ , Eric Jang∗ , Rosario Jauregui Ruano∗ , Kyle Jeffrey∗ , Sally Jesmonth∗ , Nikhil J Joshi∗ , Ryan Julian∗ , Dmitry Kalashnikov∗ , Yuheng Kuang∗ , Kuang-Huei Lee∗ , Sergey Levine∗ , Yao Lu∗ , Linda Luu∗ , Carolina Parada∗ , Peter Pastor† , Jornell Quiambao∗ , Kanishka Rao∗ , Jarek Rettinghouse∗ , Diego Reyes∗ , Pierre Sermanet∗ , Nicolas Sievers∗ , Clayton Tan∗ , Alexander Toshev∗ , Vincent Vanhoucke∗ , Fei Xia∗ , Ted Xiao∗ , Peng Xu∗ , Sichun Xu∗ , Mengyuan Yan† , Andy Zeng∗

> **VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models** 
>
> Wenlong Huang1 , Chen Wang1 , Ruohan Zhang1 , Yunzhu Li1,2 , Jiajun Wu1 , Li Fei-Fei1 1Stanford University 2University of Illinois Urbana-Champaign





This week's papers explore how robots can learn manipulation skills from large-scale, unstructured data sources like internet videos, language models, and compositional 3D representations. To be honest, the papers this week are particularly interesting and exciting to me.

***Learning Action Plan*** investigates how robots can autonomously learn action plans by analyzing **unconstrained instructional videos from the web**. The authors propose a **vision-based framework** that extracts meaningful motion primitives from videos and translates them into robotic action representations. By leveraging **semantic parsing and action segmentation**, the system enables a robot to mimic human activities without requiring **manually annotated demonstrations**. This study highlights the potential of using **internet-scale video data** for learning complex manipulation skills in an **unsupervised manner**.



***SayCan*** explores how **robotic affordances**—the physical capabilities of a robot—can be used to **ground** language-based instructions. Instead of relying on **predefined linguistic mappings**, the authors propose a **scalable approach** where a robot learns from **large datasets of human interactions** to **execute tasks based on its own capabilities**. By leveraging **RL and large-scale imitation learning**, the robot can **interpret and execute commands** that align with what it is actually capable of doing, rather than what a human might assume it can do. This paper is particularly relevant for **bridging the gap between LLMs and embodied agents**, ensuring that language instructions translate into **practical robotic actions**.





VoxPoser introduces a novel **3D spatial representation** for robotic manipulation by integrating **LLMs with voxel-based value maps**. The key innovation is the **Composable 3D Value Map**, which allows the robot to reason about **task-relevant spatial affordances** in an **interpretable** and **modular way**. Unlike traditional approaches that rely on end-to-end policy learning, VoxPoser **separates language reasoning from motion planning**, enabling **zero-shot generalization** across different manipulation tasks. This approach has exciting implications for **scaling robotic learning** and making manipulation more adaptable in real-world environments.



### **Final Thoughts**

These three papers reflect exciting advancements in robot learning from internet-scale data. The ability to learn manipulation tasks from web videos, align language with physical capabilities, and reason with spatial affordances opens up new possibilities for generalizable and scalable robotic intelligence. As someone interested in robotic manipulation, I find these approaches highly relevant—especially in my pursuit of enabling robots to master complex real-world tasks like operating an espresso machine.
