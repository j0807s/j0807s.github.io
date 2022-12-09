---
layout: page
title: Quantum Ensemble Learning
description: 
img: assets/img/overall_arch.jpg
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
    * Weaknesses : Extremely slow due to waiting cloud-based access to quantum machines from IBMQ, still vulerable to dynamically chainging machine status (i.e., noise)


#### *<u>Quantum Ensemble Learning</u>*

* In order to mitigate slow training speed and machine dependent noise, EQC proposed a framework that uses multiple quantum achine for training VQA [1].

* EQC framework updated a model with Asynchronos Stochastic Gradient Descent (ASGD), and weighted a gradient update according to each machine and its noise level with the transpiled circuit.

* $$ \theta_{t+1} = P_{correct} \alpha \theta_{t} $$

* $$ P_{correct} = e^{-CD {\mu_{t} - G_1 + \mu_{t} - G_2  \over 2} \over T_1 T_2} (1-\gamma)^{G_1} (1-\beta)^{G_2} (1-\omega)^{M} $$

* Where, $$ \alpha $$ is a learning rate, $$CD$$ means a circuit depth, $$ G_1 G_2 $$ are the number of single and dual gate operations, $$ \omega $$ is the measurement error rate and $$ M $$ is the number of measurement.

### 2. Problems & Observation

* Even though EQC framework utilized multiple quantum devices, it used quantum simulator (not a real quantum machine) to calculate the loss value during training. On the contrary, typical ensemble training requires all results from all models to calculate the loss value with simple average or majority voting (in this case, all results from all the real quantum devices).

* Without simulator, an ensemble training needs results from all the devices at every epoch, which slower the training due to another accesses to all the quantum machines.

* Also, the performance of VQA varies depending on machine status.   

### 3. Challenges & Idea

* Goal: Fast and Robust Quantum Ensemble Training with Real Quantum Machines

* Challenges:
    * (1) How to boost training speed?
    * (2) How to be robust to dynamically changing noise?

* Ideas:
    * (1) How to boost training speed?: I follow the EQC framework but the training is done with real machines, not with simulator. For further acceleration, I select a primary device which is more accessible and reliable, then aggressively optimize the given VQA for the primary device while reducing the number of total SWAP gates. This approach will reduce $$ CD $$ and $$ G_1 G_2 $$. 

    * (2) How to be robust to dynamically changing noise?:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/overall_arch.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. A conceptual illustration of proposed framework.
</div>


4. Implementations

5. Results

6. References

Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/5.jpg" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. A conceptual illustration of Variatial Quantum Algorithm learning.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %}
