---
title: Rewriting!
layout: post
---



***
```python
printf("My developer diary.\n");
```
***


Bunch of success! I'm now at a point where I've caught up with the FrontEnd and basically am only limited by what I don't know yet from their side.

My source code has been optimized to the point of having less queries to make. Originally I had queried the user information from our table aswell as an extra query to get the row names (LiveCode's inbuilt revDBquery seems to omit row names so I parsed rows manually), pasted the returned data in two different fields, then iterated over each field to replace tabs with newlines, then iterated over both fields again to combine them and put the result into another field. I then iterated yet again over that field in order to write the json we want so dearly.

Looking back that was a really awkward process but when I wrote that a week ago or so, it was the only way that made sense with my limited knowledge.

Instead I now query the database once, delimit the data with newlines and combine that with manually typed column names during a loop which also happens to write the json at the same time. Way more efficient and the code has shrunk by ~80 lines or so.

Now I want to detect new users and for that I've made some changes (everything is working) but before I finish that I first need to come up with the logic in order to achieve licensing for returning users aswell as catching new users and activating/using one of their licenses. I already have a way and it works.

With the final step being to actually write back to the database (we have a lot of options for our users and I _have_ to write every time for now). Either way UPDATE in MySQL works like a charm and it's way more straight-forward than I would have ever expected.

As for the previous post I have successfully interlinked users and multiple devices. Now I just need to catch who's who but for that I'll need to consult the FrontEnd about what they are actually inserting during the registration process. Time to take a break and call some companies.