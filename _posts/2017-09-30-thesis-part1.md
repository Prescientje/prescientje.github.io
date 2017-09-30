---
layout: post
title: "My Senior Thesis - Part 1"
date: 2017-09-30
---

## Introduction
For my senior thesis project at the Rose-Hulman Institute of Technology, I worked with Dr. Valerie Galluzzi, Dr. Matthew Boutell, and Dr. Klaus Baer to identify hand hygiene events using neural networks. Dr. Galluzzi's Ph.D. thesis focused on identifying when hospital workers washed their hands based on acceleration input from wrist sensors. She used several standard machine learning techniques to solve this problem. My work focused on applying neural networks to this problem.

## Background
Hand hygiene is a crucial part of keeping patients and healthcare workers healthy and safe. There are many guidelines on how and when workers should wash their hands, but being able to check the workers on their habits can be intrusive and would probably have too much overhead. Therefore, some level of automatic checking would be appropriate to ensure the guidelines are being followed to improve health overall. Dr. Galluzzi collected wrist acceleration data from several hospital workers, with samples of actual handwashing, random motion, and motion such as tying a shoe or unwrapping a piece of candy in order to represent confusing samples.

## Neural Networks
In one sentence, neural networks specifically work by attempting to simulate the brain's interconnected neurons through matrix multiplications. The goal of developing a neural network is to have a low error rate on novel inputs (the 'test' set) after training on inputs with known outputs (the 'training' set). There are many guides which explain neural networks and deep learning much better than I ever could, so further information is left as an exercise to the reader (and I have always wanted to say that). 

### My Models
I developed several models which I compared against each other to find their relative effectiveness. I used varying window lengths to test each model, i.e. I looked at samples that were 0.5 seconds, 1.0 second, 1.5 seconds, 2.0 seconds, as well as a few more.

 
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