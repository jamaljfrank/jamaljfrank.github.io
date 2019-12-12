---
layout: post
title:      "Trial By Fire"
date:       2019-12-12 02:58:06 +0000
permalink:  trial_by_fire
---


Finishing my first Flatiron project really challenged my patience and ingenuity. It wasn't as cut and dried as I was expecting but thats what made it fun. Here's how I progressed and some tips I'd like to pass on. Onward!


![](https://i.imgur.com/waKxOfT.jpg)


First, get invested. Whats something you're really into right now? Whats something you could use?

At the time I started my project, I was really into a video game called Fire Emblem. Fire Emblem is a tactical Role Playing Game. It has a lot of strategy involved so I'd constantly be googling to strategize. How could I make a CLI Gem around this? Easy. Make a scraper that takes some stats I'm always looking up and have them returned based on Job Class input. To be precise, I wanted to input "Archer" or "Thief" and receive all the skills of said Job Class. #ProudNerd


![](https://i.imgur.com/YQSQTHX.png)


Remember to take everything like baby steps. Personally, I have a tendency to stress myself out by trying to mentally figure everything out from the start. Instead, start by setting the basic ground work. Thankfully, we have a plethora of resources on the course page. Get as far as you can using all of them. They'll each have a slightly different angle you may need or didn't know existed. Eventually, you'll reach a point where thoughts like these will pop up:

"Why isn't this working?"

"Ah! This should work... Why isn't it working?"

"Why is it returning the whole array??"

"UGHHHHHHH!!!"


![](https://i.imgur.com/uY1YofS.png)


I reached this point when it came time to scrape websites. Honestly, I'd often get burnt out trying to figure out why a single solution wouldn't work. If that happens to you, I suggest taking a deep breath, try another approach and/or ask for help. Discuss your issue with a small study group or your cohort. Forage message boards like a civilised maniac.

There's an answer out there. Just a matter of finding it or making it yourself. 


One problem I had to face was writing methods that would assign nil values to my "Job" class if the desired data was missing from the site. Here's how I solved it: 


![](https://i.imgur.com/En9MJHf.png)


Lastly, find ways to optimize. At the time, I was in a rush to finish my project and I could've finished it much sooner but I just wouldn't be proud of it. The first version of my product would take a solid 5 seconds to load up and it was ghastly. Ultimately, I realized it did this because I'd have my gem scrape multiple URLS (36, to be exact) and store the data. I got around this by having the user input linked to a string which would then be interpolated into a URL that needed to be accessed. 


![](https://i.imgur.com/Ifmo1PU.png)


This project wasn't a walk in the park. Even this blog post took more work than I was expecting but like my project, I started with the basics. I googled how to write a blog post. Followed an outline. Wrote what I could. Googled formats. Discovered that classical music helped my focus. I continuously took baby steps. 

Recognize when you're getting overly frustrated and adapt if you don't like what you see.  

It's an ongoing struggle, but luckily, we're not alone. 



![](https://i.imgur.com/04jd8HN.jpg)


