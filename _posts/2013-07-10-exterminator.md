---
published: true
layout: post
title: Exterminator
image: agnes.jpg
---

Listening to: Lil Ugly Mane - Twistin

I recently pushed into production the latest version of the Stack Haus Buzzer, which I had to return to working on due to a bug. Essentially, the part of the app that was supposed to dial a list of numbers sequentially did so simultaneously instead. Or something to that effect- the fact that the calls looked like they were going out simultaneously may have had something to do with the heroku logs don't display any "put" commands you've made until you restart the app, at which point they display them all at the same time. In any case, it was broken and needed to be fixed. Which I did, after a few painstaking days that alternated between long periods of  picking through code and a few brief "eureka" moments. Actually, less "eureka", more "Well, that was obvious".

Anyways, it's fixed now. However the fix means I can't remove the global variables I had been using as an interim solution. So now my app uses global variables, which I'm told is a Very Bad Thing. But who cares, it works.

