---
layout: post
title: "My Senior Thesis - 1/2"
date: 2017-09-30
---

For my senior thesis project at the Rose-Hulman Institute of Technology, I worked with Dr. Valerie Galluzzi to identify hand hygiene events using neural networks.
I have used labeled data from wrist sensors containing X,Y, and Z acceleration values sampled at 100 Hz. I used varying window lengths of up to 250 samples (up to 2.5 seconds). 
Multiple models were trained to compare accuracies.
The "original" model just used the X, Y, and Z values from each hand together. 
<img src="./files/original.png" alt="Original Model" title="Original Model">

The "complex" model used the X, Y, and Z values, along with the X^2, Y^2, Z^2 values and the X*Y, Y*Z, and Z*X values to evaluate any interplay from the axes of motion.
<img src="./files/complex.png" alt="Complex Model" title="Complex Model">

The "layered" model just used the X, Y, and Z values from each hand together with one hidden layer of nodes. 
<img src="./files/layered.png" alt="Layered Model" title="Layered Model">

The "xyz" model just used the X, Y, and Z values from each hand together, but rearranged the data into "previous," "now," and "next" columns. 
<img src="./files/xyz1.png" alt="XYZ Model" title="XYZ Model">

All of these models had better-than-chance accuracy, and the results of the "both hands together tests" are summarized in the table below:
<img src="./files/recallandaccuracy.png" alt="Accuracy and Recall" title="Accuracy and Recall">

I was very shocked at the ~99% accuracy of the xyz model, and I have concluded that this is due to how I preprocessed the data: I needed to generate more hand hygiene samples, so I supersampled them at a rate such that the final split was close to 45% HH, 55% NHH. 
Due to this set up, the xyz model would have many repeated values in the HH samples, so the neural network could essentially be acting like a "repeated values detector."

After these results I developed another few models to see their results.

The "layered5" model just used the X, Y, and Z values from each hand together with five hidden layers of nodes, and is simply a deeper version of the layered model. 

Future plans are to implement other models and to make another program to analyze the effectiveness of the models. 