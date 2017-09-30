---
layout: post
title: "My Senior Thesis - Part 2"
date: 2017-10-07
---

## Recap
In my previous post I outlined the idea behind my senior thesis project and listed a few of the models I used to identify hand hygiene from wrist acceleration data.
This post probably won't make much sense without reading the previous one first.

## Results
I used two major statistical ideas to compare my models against each other. The first was recall, which is the percentage of hand hygiene samples that were accurately identified (so this value ignores the non-hand hygiene samples). The second was accuracy, which is the total number of correct results overall.

![Recall Results][recall]

![Accuracy Results][accuracy]

These results are not particularly surprising to me. The two best-performing models, L5 (Five Layered Model) and C5 (Complex Five Layered Model) were also the models with the most provision for structure and contained the most complexity. I am satisfied that all of the models performed better than chance, however.
One very interesting issue arose at sample lengths 150 and 225 (which are window lengths of 1.5 seconds and 2.25 seconds). I believe that those specific times performed much worse due to the interaction between the frequency of the handwashing motion and the window length; if that's not the case then I don't really have an idea about why those lengths were so poor relative to the others.

One other aspect I looked at was just taking a single hand at a time and getting results from there.

![Handedness Results][handedness]

Somewhat surprisingly, just looking at the right hand gave a higher accuracy than just the left hand. I supposed this difference was based on how most people are right handed, and the actions of the dominant hand must be more recognizable during handwashing compared to the other hand.

## Future Work Ideas
Unfortunately I don't see my results leading to any sudden change in the healthcare industry. Part of the problem is the initial project viability (I don't believe many doctors woud like to wear what are essentially two extra watches all the time), and of course cost is a factor.

However, there are many areas for future work to occur. One simple idea would be using different types of sensors (such as velocity, relative position between the hands, or a combination thereof). Another idea would be to use video cameras, perhaps at sink stations, to identify a worker and then check that the person is using proper technique while washing his or her hands.


## Conclusion
I hope you have enjoyed my summary of the thesis project I worked on last year. The project was definitely a new idea for me and I appreciate how much it taught me about research and deep learning itself. The code for my project is available at [another repo of mine](https://github.com/Prescientje/thesis) if you would like to take a further look!


[recall]: https://github.com/Prescientje/thesis/blob/master/images/recall2.PNG?raw=true
[accuracy]: https://github.com/Prescientje/thesis/blob/master/images/accuracy2.PNG?raw=true
[handedness]: https://github.com/Prescientje/thesis/blob/master/images/handed2c.PNG?raw=true