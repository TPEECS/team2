# team2

## Question 0: How do we draw the line between theme 1 and theme 2?
* How do we apply already known techniques? Is this low-hanging fruit vs. more involved solutions? How do we draw the line?
* “Can be demonstrated today” refers more to a proof-of-concept prototype kind of thing or practical deployment / commercialization?
We found it hard to differentiate theme 1 from theme 2, so we decided to merge them.

Approximate computing 101: What is the definition of approximate computing? Computing is approximate to begin with; digital computations in an analog world. What are the boundaries between stochastic, probabilistic, approximate? This is more of a terminology question.

How can we quantify the impact and success of approximate computing? By the extent of its adoption. Adoption implies success and accelerates advances in the field – how do we achieve that? (the whole discussion ended up trying to answer this question)
*Approximate computing should be demonstrated as a holistic approach – need to provide a systematic way to guide approximate designs (guidelines and tools) to avoid repeating ad hoc attempts. But metrics are very application-dependent / domain-specific, can we generalize? Maybe if we manage to provide frameworks that guarantees maximum performance degradation by X%. Still the same problem, how is “performance” defined across different domains? 
*For end clients, the only important metric is accuracy. Energy is something that only the system designers / service providers care about. This gap is a boundary in adoption.
*Need different interfaces/abstractions: high-level for non-experts to help them answer the question “can I even approximate?”, and more involved knobs for experts who know exactly what they are going after. What knobs are exposed to whom, and how expressive?
*Can we provide a unified quality metric to quantify the quality degradation from approximation?
*If you tell a developer today that you can tolerate up to 10% accuracy degradation, how do they even go to program under that constraint?
There are many ways to implement a certain approximation (hardware, software, mix,…). How to get from the interface/abstraction to the best implementation? We don’t want to specify how, but what. Example: there are multiple algorithms to do matrix multiplication; we pick the operation, not the algorithm. Frameworks do that selection for e.g., linear algebra domains, we need something similar.

## Engineering effort:
* For hardware approximation techniques where accuracy should dynamically adapt in runtime, need advances in reconfigurability (e.g., faster reconfig, partial reconfig for FPGAs)
* Need framework that puts together all techniques to enable programmers experiment. There are different levels of approximation: How are they interacting? Are two different techniques, synergistic or disruptive? Which one is preferable for a given use case? (e.g., hardware vs software technique that use similar principle to approximate). Ideally, investigate solutions on the Pareto frontier of accuracy and efficiency. Maybe we’ll find that all Pareto-optimal solutions are software-only 

## Overview - Need:
*API to specify approximation on computation or data
  *Different knobs for end-user and programmer
*Connection of API to underlying technique that will ultimately be used
  *Technique comparison – Pareto frontier
*Quality degradation control & metrics
