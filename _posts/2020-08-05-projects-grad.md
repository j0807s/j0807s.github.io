---
layout: post
title: "Graduation Project"
categories: [projects]
comments: true
---
* #### Idea: detected row hammer attack using MLP(Multi Layer Perceptron) in memory controller
* #### Motivation 1 : Revisiting RowHammer(ISCA2020) showed only 10K activation can cause RowHammer bitflips
* #### Motivation 2 : Related researches(PARA, ProHIT, MRLop) have a lack of detecting malwares and cause much powerconsumption all the time
* #### Still working on this (from 2020-08-05)

<!--more-->
* #### Detailed Motivation: DRAM has suffered from the severe reliability problem; repetitive access to the same rows in DRAM can cause losing data. Also, the newer DRAM chips are more vulnerable to Rowhammer bitflip, indicating that attackers can destroy the memory system in more various ways if the device feature size reduces. I am currently trying to solve this problem using machine learning as a graduation project, based on the fact that machine learning models have powerful capabilities to learn complex patterns. 