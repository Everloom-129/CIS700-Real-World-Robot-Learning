# Learning from Synthetic Data I

Tony Wang

03/18/2025



## Essay

Today's papers focus on sim-to-real transfer, specifying how to bridge the gap between robot learning and our real world. 



First up is **ActuatorNet**, from ETH Zurich and Intel. This work got me excited about reinforcement learning (RL) for agile, legged robots, specifically ANYmal, a dog-sized quadruped. Traditionally, training RL policies directly on physical robots is slow and risky, but these researchers cleverly combined classical physics simulations with a learned neural network model of actuator dynamics—what they call an "actuator net". This hybrid approach lets ANYmal learn complex motor skills entirely in simulation. The kicker? The policy transfers seamlessly to reality, enabling impressive feats like dynamic recovery from falls and faster locomotion than hand-engineered controllers. It's an elegant approach that neatly sidesteps the usual hurdles of sim-to-real.



The second paper, **"Blind Quadrupedal Locomotion,"** also from ETH Zurich, blew me away by training ANYmal robots to navigate tough, unpredictable terrains—think mud, snow, and even running water—using only proprioception (internal body sensing) without external visual feedback. The key innovation here is the use of privileged learning and a clever terrain-generation curriculum. Initially, a teacher policy trained with extra environmental information quickly learns effective locomotion. Then, this knowledge is distilled into a student policy that uses only proprioception. The result? Robust, zero-shot generalization to totally unseen real-world terrains. Watching ANYmal confidently stroll through mud or thick vegetation makes me eager to explore similar approaches in my own projects.



Lastly, NVIDIA's **DeXtreme** paper tackles dexterous in-hand manipulation—a notoriously tough task for robots. Instead of using expensive hardware or complex marker-based tracking setups (like previous approaches), they achieve impressive object reorientation using the affordable Allegro Hand and a purely vision-based pose estimator powered by three off-the-shelf cameras. This setup, trained in NVIDIA's Isaac Gym simulator with extensive domain randomization, matches or even surpasses earlier methods relying on more complex systems. Their straightforward yet powerful vision pipeline particularly grabbed my attention—it's encouraging for those of us working in constrained lab environments.



How to engineer the simulation, how to set up learning strategy, how to utilize 110% of the hardware, all these are open problem towards sim2real robot learning. We have gone far beyond the early stage and it's time to dream next big dream: Cosmos, Genesis, etc. We will make difference. 





## Course Notes



### Pain of Sim2Real

> *Antonio share sad story behind his sim2real drone racing projects...*

1. many calibration
2. infinite config file
3. many system identification plots -> weird noise, non-differentiable dynamics...
   - 1965 paper on dynamic modeling with sys state identification





### Jump of Sim2Real

- less fidelity need 
- more consumer grade robot
  - aka unitree etc
- little algo innovation

- 

Dinesh disagree on the slides about dex contact rich interaction

- rotating the objects with robot hand like LEAP
- slippery rocks....
- 4 points, very localized tasks? 



Antonio: cooking a pizza etc, is far from what we can 



