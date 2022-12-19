---
layout: page
title: Pruning for QNN 
description: 
img: assets/img/prj2_implementation.png
importance: 2
category: work
---

### 1. Context

#### *<u>Quantum Machine Learning</u>*

* Quantum machine learning is one of the promising applications for Noisy Intermediate-Scale Quantum devices, which have a small number of noisy qubits 

* Quantum machine learning trains Parameterized Quantum Circuit (PQC) that have trainable parameterized gates following the optimization process of machine learning

### 2. Problems & Observations

* Observed huge training speed gap (2000x) between PQCs and classical neural networks that have the similar number of parameters

* Training time exponentially grows with the number of parameters

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj_observation.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. Comparison of training time between Parameterized Quantum Circuits (PQC) and classical neural networks according to the number of parameters. While the training time of classical neural network remains constant, the training time of PQCs grows exponentially when the number of parameters increases 
</div>

### 3. Ideas

* Reduce a number of parameters with a pruning apporach

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj2_implemenation.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 2. An illstration of how pruning works for Parameterized Quantum Circuit (PQC)
</div>

### 4. Evaluation Methodolgy
* Optimizer: SGD, Pruning ratio: 20%, Loss: CrossEntropy Dataset: downsampled binary MNIST (0,1), Evaluated circuit: circuit 1, 3, 5, 9 from [1]


### 5. Results
* With pruning ratio 0.2, the idea achieved an average accuracy improvement of 2% and training time reduction of 17%

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj2_results_1.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj2_result_2.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 2. Effect of pruning approach on training speed and accuracy
</div>


### 6.Discussion & Future work
* Weight pruning: In this project, I used a random pruning before training. However, there are a plenty of pruning methods that can be explored for PQC compression. Especially, weight pruning, which eliminates small weight parameters, is a straightforward to apply

* Adjusting number of qubits: The number of parameters not only increases with the number of PQC layers but also with the number of qubits

* Experiments using real quantum machines: pruning redundant parameterized quantum gates will improve the performance due to reduced gate error and noise

### 7. References
[1] Sim, Sukin, Peter D. Johnson, and Alán Aspuru‐Guzik. "Expressibility and entangling capability of parameterized quantum circuits for hybrid quantum‐classical algorithms." Advanced Quantum Technologies 2.12 (2019): 1900070.
