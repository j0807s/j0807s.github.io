---
layout: page
title: Quantum Ensemble Learning
description: 
img: assets/img/overall_arch.png
importance: 1
category: work
---

### 1. Context

#### *<u>Variational Quantum Algorithm</u>*

* Quantum supremacy algorithms (e.g., Shor's and Grover's) require ~ $$ 10^6 $$ error-tolerant qubits, which is infeasible to run on Noisy-Intermediate-Scale Quantum (NISQ) devices that provide 100-1000 error-prone qubits.

* Whereas, Variational Quantum Algorithms (VQA) can potentially take advantage of NISQ devices by exploiting parameterized gates. Since their parameters can be dynamically adjusted, VQAs are robust to noise and can be designed to achieve quantum superiority with NISQ devices.

* Now, we have three VQAs : Variational Quantum Eigensolver (VQE), Quantum Approximate Optimization Algorithm (QAOA), Quantum Neural Network (QNN). Optimizing parameterized gates in VQAs is following the optimization loop just like machine learning.



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/VQA_context.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. A conceptual illustration of Variatial Quantum Algorithm learning.
</div>

#### *<u>Training Quantum Neural Network</u>*

* Training VQA is categorized into two parts:

* (1) Training on a classical computer, Inferencing on a quantum computer
    * Strengths : Fast
    * Weaknesses : Not scalable, hard to capture device specific noise effect

* (2) Training on a quantum computer, Inferencing on a quantum computer
    * Strenths : Scalable, robust to noise
    * Weaknesses : Extremely slow due to waiting cloud-based access to quantum machines from IBMQ, still vulerable to dynamically chainging machine status (i.e., noise level)


#### *<u>Quantum Ensemble Learning</u>*

* In order to mitigate slow training speed and machine dependent noise, EQC proposed a framework that used multiple quantum achine for training VQA [1].

* EQC framework updated a model with Asynchronos Stochastic Gradient Descent (ASGD), and weighted a gradient update according to each machine and its noise level with the transpiled circuit.

* $$ \theta_{t+1} = P_{correct} \alpha \theta_{t} $$

* $$ P_{correct} = e^{-CD {\mu_{t} - G_1 + \mu_{t} - G_2  \over 2} \over T_1 T_2} (1-\gamma)^{G_1} (1-\beta)^{G_2} (1-\omega)^{M} $$

* Where, $$ \alpha $$ is a learning rate, $$CD$$ means a circuit depth, $$ G_1 G_2 $$ are the number of single and dual gate operations, $$ \omega $$ is the measurement error rate and $$ M $$ is the number of measurement.

### 2. Problems

* Even though EQC framework utilized multiple real quantum devices, it used a quantum simulator to calculate the loss value during training. Thus, EQC is not scalable.

* While a typical ensemble training needs results from all the devices at every epoch, which is slow due to another accesses to all the quantum machines.

* Also, the performance of VQA varies depending on dynamically changing machine noise.

* *<u>Problems</u>*
* (1) Quantum ensemble training with accessing all quantum machines is expensive (i.e., time-consuming).
* (2) When the noise level becomes different, the performance of the learned model varies.

### 3. Challenges & Idea

* Challenges:
    * (1) How to boost quantum ensemble training? 
    * (2) How the model to be robust against the dynamically changing noise?

* Ideas:
    * (1) Topolgies-aware optimization and (2) noise-aware training/inference

    * Under the EQC framework without using simulator, the proposed framework selects a primary device which is more reliable and more accessible among all given devices. Then, it resynthesizes the given circuit toward topologies-friendly circuit that has samller number of total SWAP gates. This approach reduces the above $$ CD $$ and $$ G_1 G_2 $$, which means the new circuit is likely to converge faster. Re-synthesized circuit should have the similar expressibility and entangling capability with the original circuit.

    * According to the Pauli Twirling Approximation (PTA), the effect of Pauli errors is the random insertion of Pauli X, Y, and Z gates to the model with a probability distribution of a device. Thus, my framwork randomly inserts Pauli gates during training and inference on other devices as much as the distribution difference between the primary device and others.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/overall_arch.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 2. A conceptual illustration of proposed framework.
</div>


4. Implementations

5. Results

6. References
