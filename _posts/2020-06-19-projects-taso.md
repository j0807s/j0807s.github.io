---
layout: post
title: "Accelerating Deeplearning Workloads using Compiler"
categories: [projects]
comments: true
---

* #### Conducted in Cass Lab in Hanyang University, Advised by Prof. Yongjun Park
* #### Problem : Observated TASO(SOSP, 2019) was not able to generate optimal computation graphs for CPU
* #### Idea : Automatically generates optimal computation graphs for inference on CPU
* #### ![]({{ site.url }}/img/TASO_ORIGINAL.JPG)
* #### ![]({{ site.url }}/img/TASO_RESULT.PNG)

<!--more-->

#### 1. What is TASO?
* #### TASO is the framework which optimizes the computation graphs of DNN models using automatically generated and verified graph transformations.
* #### Here is the paper [TASO_SOSP2019]({{ site.url }}/img/TASO.pdf)
* #### ![]({{ site.url }}/img/TASO_Workload.PNG)

#### 2. Problem
* #### TASO can optimize computation graphs for the certain GPU architectures; TASO requires at least 6GB of GDDR

#### 3. Idea
* #### Build a framework that automatically generates optimal computation graphs for inference on CPU
* #### Wimpy cores need small and optimal computation graphs for an inference



