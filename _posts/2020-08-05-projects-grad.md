---
layout: post
title: "Detecting Rowhammer bitflips using ML"
categories: [projects]
comments: true
---
* #### Problem : Revisiting RowHammer(ISCA'2020) showed only 10K activations can cause RowHammer bitflips and indicated that rowhammer threshold decreases if the device feature size gets smaller
* #### Observation : Related works(Deterministic, Probabilistic approach)' area and energy overhead increased or their performance became lower when the rowhammer threshold decreased
* #### Idea: Detecting rowhammer bitflips using ML
* #### Implementation : Still working on this (since 2020-09-01)

<!--more-->
* #### Detailed Motivation: DRAM has suffered from the severe reliability problem; repetitive access to the same rows in DRAM can cause losing data. Also, the newer DRAM chips are more vulnerable to Rowhammer bitflip, indicating that attackers can destroy the memory system in more various ways if the device feature size reduces. I am currently trying to solve this problem using machine learning as a graduation project, based on the fact that machine learning models have powerful capabilities to learn complex patterns. 