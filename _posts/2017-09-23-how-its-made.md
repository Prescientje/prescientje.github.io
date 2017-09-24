---
layout: post
title: "How I made this blog"
date: 2017-09-23
---

I have known that I wanted to have a blog for a while now. I enjoy both the computer science aspect of coding/designing the website as well as getting a chance to share my viewpoints with the world. 

Because I majored in Computer Science ([International Computer Science](http://www.rose-hulman.edu/academics/academic-departments/computer-science-software-engineering/majors-and-minors.html#international-computer-science) as a matter of fact), I could not let myself just make a simple Wordpress or Blogspot site.
I had already set up a GitHub Pages site earlier as a quick weekend project, so I decided to basically wipe that repo and start fresh.
Because GitHub pages allows for easy Jekyll integration, I decided to just go with that for the time being.

After trying out the [Jekyll Quick Start Guide](https://jekyllrb.com/docs/quickstart/) and running into problems regarding my older version of Linux, I searched around for some other guides.
I was primarily searching for guides which simply described the file set up instead of installing Jekyll, testing the site, and then uploading it to GitHub Pages.
I looked into the [Poole Project](https://github.com/poole/poole) but eventually found [Jonathan McGlone's very helpful guide](http://jmcglone.com/guides/github-pages/).
He walks through each step in extremely helpful detail and provided several interesting suggestions to add to a blog at the end of the guide. 

Making a custom domain was more nerve-wracking but actually ended up being a bit easier. I bought this domain and then after being initially confused by the [guide on GitHub itself](https://help.github.com/articles/using-a-custom-domain-with-github-pages/), I searched for more.
I found [Julia Lovett's guide](https://medium.com/@LovettLovett/github-pages-godaddy-f0318c2f25a) and combined that with the guide from GitHub and was able to figure it out.
Because the guide from Julia is from 2014, the screenshots are bit out of date, so here is the key piece with my screenshot:

![Godaddy Settings][pic1]

After navigating to My Products, click the DNS button on the right of the domain listing. 
Then you will want to:
* set the A record to point to 192.30.252.153
* set the www record to point to username.github.io
Somewhere I heard or read that it could take up to 24 hours for everything to connect together, but for me it worked within about 5 minutes.

I hope you enjoyed this guide and if you have further questions feel free to contact me on [Twitter](https://twitter.com/ajamesedwards).

[pic1]: https://github.com/Prescientje/prescientje.github.io/blob/master/images/20170923/godaddy.png?raw=true
