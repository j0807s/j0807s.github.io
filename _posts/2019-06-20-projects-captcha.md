---
layout: post
title: "CAPTCHA PROJECT : Building a Machine Reads Distorted Text"
categories: [projects]
comments: true

---

* #### Achieved 99% of the accuracy 
* #### Problem : A small train set which caused overfitting and low accuracy
* #### Idea : Used data augmentation and Transfer Learning to avoid overfitting while increasing the accuracy 
* #### Result :
* #### ![]({{ site.url }}/img/CAPTCHA.JPG)
* #### ![]({{ site.url }}/img/Models_compare.PNG)
* #### ![]({{ site.url }}/img/Models_result.PNG)

<!--more-->
* #### Implementation:
1. ##### Preprocessing: ![]({{ site.url }}/img/Preprocessing.PNG)
        * ##### a) Image Thresholding 
        * ##### b) Removing small objects from the image 
        * ##### c) Cropping useless part of the image 
        * ##### d) Cropping the image into 5 pieces 
2. ##### Data augmentation: 
        * ##### Data augmentation is a strategy that increases the diversity of data available for training models, without actually collecting new data.
        ![]({{ site.url }}/img/CAPTCHA.JPG) 
3. ##### Transfer learning: 
        * ##### Transfer learning is a machine learning method where a model developed for a task is reused as the starting point for a model on a second task. ![]({{ site.url }}/img/Transferlearning.PNG)





