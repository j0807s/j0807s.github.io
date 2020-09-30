---
layout: post
title: "CAPTCHA PROJECT : Building a Machine Reads Distorted Text"
categories: [projects]
comments: true

---
* #### Built a system that can read distorted text 
* #### Problem : A small train set(only 1000 samples) caused overfitting and a low accuracy
* #### Idea : Increased the amount of the training set to avoid overfitting
* #### Implementation : Used data augmentation approach and Transfer Learning
* #### Contribution : Achieved the highest score at the class kaggle competition with only 1000 training samples (dataset from Wilhelmy, Rodrigo Rosas, Horacio)
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





