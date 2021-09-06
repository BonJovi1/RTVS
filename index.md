## RTVS: A Lightweight Differentiable MPC Framework For Real-Time Visual Servoing

Mohammad Nomaan Qureshi<sup>\*</sup><sup>1</sup>, Pushkal Katara<sup>\*</sup><sup>1</sup>, Abhinav Gupta<sup>\*</sup><sup>1</sup>, Harit Pandya<sup>2</sup>, Y V S Harish<sup>1</sup>, AadilMehdi Sanchawala<sup>1</sup>, Gourav Kumar<sup>3</sup>, Brojeshwar Bhowmick<sup>3</sup> and K. Madhava Krishna<sup>1</sup>

<div align="center">
<sup>1</sup> Robotics Research Center, IIIT Hyderabad, India <br> 
<sup>2</sup> Toshiba Research, Cambridge, UK <br> 
<sup>3</sup> TCS Research and Innovation, Kolkata, India <br>
<sup>*</sup> indicates equal contribution <br>
</div>

Coda and Dataset will be released soon!

<div align ="center">
<button name="button" onclick="https://bonjovi1.github.io/assets/pdf/RTVS.pdf">Download Paper</button>
</div>

<p align="center">
<img src="video.gif" /> 
</p>

### Abstract

Recent data-driven approaches to visual servoing have shown improved performances over classical methods due to precise feature matching and depth estimation. Some recent servoing approaches use a model predictive control (MPC) framework which generalise well to novel environments and are capable of incorporating dynamic constraints, but are computationally intractable in real-time, making it difficult to deploy in real-world scenarios. On the contrary, single- step methods optimise greedily and achieve high servoing rates, but lack the benefits of the MPC multi-step ahead formulation. In this paper, we make the best of both worlds and propose a lightweight visual servoing MPC framework which generates optimal control near real-time at a frequency of 10.52 Hz. This work utilises the differential cross-entropy sampling method for quick and effective control generation along with a lightweight neural network, significantly improving the servoing frequency. We also propose a novel flow normalisation layer which ameliorates the issue of inferior predictions from the flow network. We conduct extensive experimentation on the Habitat simulator and show a notable decrease in servoing time in comparison with other approaches that optimise over a time horizon. We achieve the right balance between time and performance for visual servoing in six degrees of freedom (6DoF), while retaining the advantageous MPC formulation.


<p align="center">
<img src="Teaser.png" alt="drawing" width="600"/> 
</p>

<p align="center">
RTVS shows a significant improvement in servoing frequency vis-à-vis other deep MPC based visual servoing approaches in 6DoF, without compromising its ability to attain precise alignments. Our controller generates optimal control in real-time at a frequency of 66 Hz (excluding optical flow overheads) and successfully servos to its destination, while other approaches still lag behind.
</p>

### Pipeline
We demonstrate our MPC based optimisation framework to perform visual servoing in 6DoF. In each MPC optimisation step, we use FlowNetC to predict the optical flow between the current image It and goal image I∗, which acts as the target flow for control generation. The flow computed between the current and previous image acts as a proxy for depth, which after normalisation, is fed into the interaction matrix. Our control generator then optimises the flow loss to generate control commands. 

<p align="center">
<img src="main_final.png" alt="drawing" width="600"/>
</p>

This figure depicts our control generation architecture. We sample a (β x 6) vector from a multivariate Gaussian distribution and pass it through our Directional Neural Network. The kinetic model generates β pseudo-flows and the flow loss is computed for each, against the target flow. In each MPC step, we pick the top K velocities corresponding to the K least flow errors to update the Gaussian parameters, while the mean velocity is fed to the actuator.
<p align="center">
<img src="generatorv5.png" alt="drawing" width="500"/>
</p>

