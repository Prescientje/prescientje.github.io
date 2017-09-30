---
layout: post
title: "My Senior Thesis - Part 2"
date: 2017-10-07
---

## Recap
In my previous post I outlined the idea behind my senior thesis project and listed a few of the models I used to identify hand hygiene from wrist acceleration data.
This post probably won't make much sense without reading the previous one first.

## 
All of these models had better-than-chance accuracy, and the results of the "both hands together tests" are summarized in the table below:
<img src="./files/recallandaccuracy.png" alt="Accuracy and Recall" title="Accuracy and Recall">

I was very shocked at the ~99% accuracy of the xyz model, and I have concluded that this is due to how I preprocessed the data: I needed to generate more hand hygiene samples, so I supersampled them at a rate such that the final split was close to 45% HH, 55% NHH. 
Due to this set up, the xyz model would have many repeated values in the HH samples, so the neural network could essentially be acting like a "repeated values detector."

After these results I developed another few models to see their results.

The "layered5" model just used the X, Y, and Z values from each hand together with five hidden layers of nodes, and is simply a deeper version of the layered model. 

Future plans are to implement other models and to make another program to analyze the effectiveness of the models. 