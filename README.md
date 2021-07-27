# RTVS
[IROS '21] RTVS: A Lightweight Differentiable MPC Framework For Real-Time Visual Servoing

Mohammad Nomaan Qureshi*, Pushkal Katara*, Abhinav Gupta*, Harit Pandya, Y V S Harish, AadilMehdi Sanchawala, Gourav Kumar, Brojeshwar Bhowmick and K. Madhava Krishna

Some project pages to refer to:
- https://hbutsuak95.github.io/AutoLay/
- https://montrealrobotics.ca/probod/

We need to set up GitHub pages and this will automatically get hosted on Abhinav's github.io website! 

### Abstract

Recent data-driven approaches to visual servoing have shown improved performances over classical methods due to precise feature matching and depth estimation. Some recent servoing approaches use a model predictive control (MPC) framework which generalise well to novel environments and are capable of incorporating dynamic constraints, but are computationally intractable in real-time, making it difficult to deploy in real-world scenarios. On the contrary, single- step methods optimise greedily and achieve high servoing rates, but lack the benefits of the MPC multi-step ahead formulation. In this paper, we make the best of both worlds and propose a lightweight visual servoing MPC framework which generates optimal control near real-time at a frequency of 10.52 Hz. This work utilises the differential cross-entropy sampling method for quick and effective control generation along with a lightweight neural network, significantly improving the servoing frequency. We also propose a novel flow normalisation layer which ameliorates the issue of inferior predictions from the flow network. We conduct extensive experimentation on the Habitat simulator and show a notable decrease in servoing time in comparison with other approaches that optimise over a time horizon. We achieve the right balance between time and performance for visual servoing in six degrees of freedom (6DoF), while retaining the advantageous MPC formulation.

### Results

### Citation

```
@misc{mnqureshiRTVS,
title={RTVS: A Lightweight Differentiable MPC Framework For Real-Time Visual Servoing}, 
author={Mohammad Nomaan Qureshi and Pushkal Katara and Abhinav Gupta and Harit Pandya and YVS Harish and AadilMehdi Sanchawala and Gourav Kumar and Brojeshwar Bhowmick and K. Madhava Krishna},
year={2021}
}

```
### Acknowledgement

We thank Tata Innovation Labs, Kolkata for funding our project. 

