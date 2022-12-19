---
layout: page
title: Pruning for QNN 
description: 
img: assets/img/pruned_circuit1.png
importance: 2
category: work
---

### 1. Context

#### *<u>Quantum Machine Learning</u>*

* Quantum machine learning is one of the promising applications for Noisy Intermediate-Scale Quantum devices, which have a small number of noisy qubits. 

* 


### 2. Problems & Observations

* Huge training speed gap(2000x) between PQCs and classical neural networks that have similar number of parameters

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj2_observation.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 1. Observation
</div>

### 3. Ideas

* Reduce a number of parameters with pruning apporach 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/pruned_circuit1.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 2. A pruning approach for QNN
</div>

### 4. Evaluation Methodolgy
* Optimizer: SGD, Pruning ratio: 20%, Loss: CrossEntropy Dataset: downsampled binary MNIST (0,1), Evaluated circuit: circuit 1, 3, 5, 9 described above


### 5. Results

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/prj2_results.png" title="context" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig 3. Comparision between original circuits and pruned circuits
</div>

### 6. References
