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
        {% include figure.html path="assets/img/prj2_observation.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. Observation
</div>

### 3. Ideas

* Reduce a number of parameters with a pruning apporach

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj2_implemenation.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 2. A pruning approach for QNN
</div>

### 4. Evaluation Methodolgy
* Optimizer: SGD, Pruning ratio: 20%, Loss: CrossEntropy Dataset: downsampled binary MNIST (0,1), Evaluated circuit: circuit 1, 3, 5, 9 from [1]


### 5. Results

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj2_results.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 3. Comparision between original circuits and pruned circuits
</div>

### 6.Discussion & Future work

### 7. References
[1] Sim, Sukin, Peter D. Johnson, and Alán Aspuru‐Guzik. "Expressibility and entangling capability of parameterized quantum circuits for hybrid quantum‐classical algorithms." Advanced Quantum Technologies 2.12 (2019): 1900070.
