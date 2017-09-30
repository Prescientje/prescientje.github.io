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

## My Models
I developed several models which I compared against each other to find their relative effectiveness. I used varying window lengths to test each model, i.e. I looked at samples that were 0.5 seconds, 1.0 second, 1.5 seconds, 2.0 seconds, as well as a few more. Below are a few illustrations of how the various models are connected with their particular features.

To develop these models, I used [Tensorflow, a Google Deep Learning library](https://www.tensorflow.org/). The overall flow of my program is summarized in the following diagram:

![Pipeline Flow][flow]

I preprocessed the data, then formatted it based on the window length mentioned above. Then I pushed it through Tensorflow for a while (several epochs of backpropagation), each step ideally increasing accuracy in the model. Then finally the model was tested with the test set to produce an actually percentage accuracy with which I could compare it against the other models.  

### The Original Model

![Original Model][original]

Here the X, Y, and Z data for each hand were put into separate matrices, which were then connected together to obtain an output.

### The Complex Model

![Complex Model][complex]

The "complex" model used the X, Y, and Z values, along with the X^2, Y^2, Z^2 values and the X\*Y, Y\*Z, and Z\*X values to evaluate any interplay from the axes of motion.

### The Layered Model

![Layered Model][layered]

The "layered" model just used the X, Y, and Z values from each hand together with one hidden layer of nodes. 

### The Five Layered Model

![Five Layered Model][layered5]

This model simply added layers to the Layered Model in order to (hopefully) increase accuracy even further.

My next post will summarize my results and offer some ideas for future work.

[flow]: https://github.com/Prescientje/thesis/blob/master/images/pipeline3.png?raw=true
[original]: https://github.com/Prescientje/thesis/blob/master/images/original.png?raw=true
[complex]: https://github.com/Prescientje/thesis/blob/master/images/complex.png?raw=true
[layered]: https://github.com/Prescientje/thesis/blob/master/images/layered.png?raw=true
[layered5]: https://github.com/Prescientje/thesis/blob/master/images/layered5.png?raw=true