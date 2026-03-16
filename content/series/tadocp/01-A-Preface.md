+++
draft          = false
title          = "The Art and Design of Computer Programs"
episode_number = 1
description    = "An introduction to the series and the philosophy of principled programming."
youtube_url    = ""
exercises      = []
resources      = [
  {title = "Beej's Guide to C Programming",                              url = "https://beej.us/guide/bgc/html/split/index.html"},
  {title = "Effective C: An Introduction to Professional C Programming", url = "https://www.amazon.com/Effective-Introduction-Professional-Robert-Seacord/dp/1718501048"},
  {title = "The C Programming Language",                                 url = "https://www.amazon.com/gp/product/0131103628"},
  {title = "C Programming: A Modern Approach",                           url = "http://knking.com/books/c2/index.html"},
  {title = "Modern C",                                                    url = "https://inria.hal.science/hal-02383654"},
  {title = "The C Book",                                                  url = "https://publications.gbdirect.co.uk/c_book/"},
  {title = "Bro Code: C Programming Course",                             url = "https://www.youtube.com/watch?v=xND0t1pr3KY"},
  {title = "FreeCodeCamp: C Programming Course",                         url = "https://www.youtube.com/watch?v=KJgsSFOSQv0"},
  {title = "Harvard CS50: C Programming",                                url = "https://www.youtube.com/watch?v=ix5jPkxsr7M"},
  {title = "C Lang Org References",                                       url = "https://www.c-language.org/resources"},
  {title = "LeetCode Exercises",                                          url = "https://leetcode.com/"},
  {title = "Awesome C",                                                   url = "https://github.com/inputsh/awesome-c#readme"},
  {title = "C Projects and Tutorials",                                    url = "https://github.com/nCally/Project-Based-Tutorials-in-C"},
]
tags = ["tadocp"]
+++
## Video Link

## "Let There Be Light!"

There is something special about light. 

Many societies and cultures have myths about it: From Prometheus and fire, to stories about the sun and the moon. So beloved is our most basic contrast: Light and Dark, that it appears even in our most complex devices.

Computers live through 1s and 0s, called **binary**. This binary, grouped into **bytes** is the foundation of all computing (Well, there's a bit more to it than that, but we'll explore that later.)

Computers rely on bottled lightning to do things like find new proteins for cancer research, model weather to save lives during disasters, and command an army of bots to push disinformation over the course of 10 years, such that the global order breaks down and results in total nuclear destruction.

> *"Brilliant!" Said the Caveman Urga, "You Make Fire Do Thing, Now Humanity Will Collapse!"*

Like fire, computers have changed the landscape of our entire world. We have made so many strides in it all, and yet, we are now at risk of losing the very skills needed to continue developing new tools and systems that can also radically alter the landscape of the world.

Case in point: Generative AI.

![image](/imgs/scamaltman.png "Scam Altman Does It Again")

Many developers are choosing to sacrifice their knowledge in the name of vibes, choosing the way of sloppy ease, rather than detailed, well-organized design. The result are increased bugs, security holes, downtime and outages in critical system, broken systems, and entire applications that simply no longer function. The art of developing services and systems is still present, but as the number of older grey-bearded educators retire or pass away, there aren't people rising up to replace them.

Large tech firms, once the mass-hiring, forward-moving organizations having firing at increasing rates. Outages and downtimes persist, often in dramatic fashion. Microsoft has altogether given up building any decent product and the end result is garbage. slop. trash. pointless.

To call it engineering is a myth. Engineering presumes that the one doing it is building with well-documented, stable, foundational knowledge. But with so few Computer Science degree-holders finding jobs, and those jobs are more at risk of being migrated either into the loving arms of claude or some cubicle in indopacom sphere due to companies always needing to increase return on investment and reduce costs, the once capable replacements for the Linus Torvalds, Denise Ritchies, and Ken Thompsons of the world are shuffling off to find new lines of work that hopefully won't get eaten by the six-fingered black hole that is AI.

## It's Wizard Time Mother-Trucker!

The need to return to a more principled era is upon us, now more than ever. We do not call it engineering for no reason: To engineer is to design with stability and core principles in mind, not as an afterthought. 

As a result of this, I have been frequently thinking about [this old MIT course a lot](https://ocw.mit.edu/courses/6-001-structure-and-interpretation-of-computer-programs-spring-2005/video_galleries/video-lectures/). The videos and technology are long outdated, Don't tell Common LISP fans that, but there is something charming about the methodology of the principles: Seeing programming as wizardry. 

Magic may feel inaccessible to the unfamiliar, but to the trained and careful, wizardry is nothing more than the crafting of logic to meet one's ends. Even if that end is finding some way to drain some loser's bitcoin wallet to zero. To that end, I have started this series as a way to return to these principles and in some small measure, fight back against the vibes-based nonsense that is sweeping the USA.

## Intelligence Is Your Birthright

Within the Biblical canon is a story about Esau and Jacob. Esau, the firstborn of his father Isaac, was set to attain the rights and priviledges from his father and grandfather. However, he is stupid and thoughtless. Contrast this with his younger brother Jacob. Jacob is wise, thoughtful, crafty, and capable. As a result, Jacob desires his brother's birthright while Esau takes it for granted. In the end, Jacob approaches Esau one day, who is quite hungry, and offers to sell Esau some food in exchange for his birthright. Esau takes the deal, but ultimately regrets it, begging his father for a blessing. Isaac, irate though loving, offers Esau an inferior blessing.

Make no mistake, AI is not your birthright, your knowledge and intelligence are. Generative AI is not what you are destined recieve: your humanity, creativity, and ability are. Your intelligence is your birthright. Do not sell it for a simple bowl of stew because you are hungry for something more than bread. And make no mistake, to use Generative AI to perform your thinking, your writing, your art, your creativity is cause you to lose your ability [to think](https://time.com/7295195/ai-chatgpt-google-learning-school/), [to grow](https://www.mdpi.com/2075-4698/15/1/6), [to learn](https://www.media.mit.edu/publications/your-brain-on-chatgpt/), [to create](https://www.forbes.com/sites/chriswestfall/2024/12/18/the-dark-side-of-ai-tracking-the-decline-of-human-cognitive-skills/).

Do not sell your birthright for a mess of stew just because you are hungry for steak. Choose to keep your intelligence, your humanity, your ability. Your skills. AI is useful, it is a tool, which, when used correctly, can help find discoveries and make new connections. But it must be understood and used accordingly.


I digress.

# C IS GOD'S PROGRAMMING LANGUAGE

The language of our choosing is the C Programming language. I have several reasons for this, namely it forces you to learn twice as much as you would want to, and bugs that crop up require a careful eye, something that AI might not be able to implicitly be able to catch. To really master C, you will, in fact, have to "git gud."

During this series, I want you to avoid AI, for the reasons I have mentioned above, but also because I want you to learn things. AI cannot learn things for you. Only you can learn things for you. And I want you to believe in your own ability, your own intelligence, and own skills.

## Resources for Learning

I am not the only person who has taught courses similar to this, and I will not be the last. As such, there are a number of books, videos, articles, guides, and so forth that can help you learn, develop, and grow your skills as both a user, and as a learning programmer. 

**NOTE: You want to avoid always relying on tutorials to learn things. Practice problems, projects, and exercises should come from you, not from AI, not from a tutorial. this is because you want to avoid [TUTORIAL HELL](https://www.reddit.com/r/learnprogramming/comments/188ated/what_exactly_is_tutorial_hell/).**

You can avoid this problem by using these resources when you need them, then stopping once you have learned/come to the solution on your own. There is nothing more satifying than having built something on your own.

### Books and Guides

- [Beej’s Guide to C Programming](https://beej.us/guide/bgc/html/split/index.html)

- [Effective C: An Introduction to Professional C Programming](https://www.amazon.com/Effective-Introduction-Professional-Robert-Seacord/dp/1718501048)

- [The C Programming Language](https://www.amazon.com/gp/product/0131103628)

- [C Programming: A Modern Approach](http://knking.com/books/c2/index.html)

- [Modern C](https://inria.hal.science/hal-02383654)

- [The C Book](https://publications.gbdirect.co.uk/c_book/)


### Video Series
- [Bro Code: C Programming Course](https://www.youtube.com/watch?v=xND0t1pr3KY)

- [Free Code Came: C Programming Course](https://www.youtube.com/watch?v=KJgsSFOSQv0)

- [Harvard's CS50: C Programming](https://www.youtube.com/watch?v=ix5jPkxsr7M)

### Other Resources and Tools:

- [C Lang Org References](https://www.c-language.org/resources)

- [LeetCode Exercises Website](https://leetcode.com/)

- [Awesome C](https://github.com/inputsh/awesome-c#readme)

- [C Projects and Tutorials](https://github.com/nCally/Project-Based-Tutorials-in-C)



