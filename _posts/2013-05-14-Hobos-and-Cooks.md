---
layout: post
title: Hobos and Cooks
summary: Dealing with Windows
image: hockney.jpg
---	

I've starting trying to set up my computer in order to work on Contractually, one of the startups that resides in the Stackhaus, and, to put it mildly, my choice of OS is hindering my progress. I keep running into problems for which there is only one solution- stop using Windows. In particular, there are a few Ruby gems that detest Windows. I considered setting up a dual-boot of Linux Mint 14 alongside my pre-existing installation of Windows 7, but I ran into other issues. HP, in their infinite wisdom, inserts a HP Tools partition in the hard drives of HP PC's. Now, most Windows computers already ship with three partitions used up- C, System and Recovery- so the HP Tools partition means that all four available partitions have been taken by the time the computer is in the customer's hands. I really didn't feel like messing around with deleting the System or Recovery partitions, considering I don't have a recovery disk available to me (I asked my colleague for a DVD. "What's a DVD?").

Thankfully there is another solution, one provided to me by the aforementioned colleague. Vagrant! Using this in combination with Chef, I will hopefully be able to install all the gems I need (kgio is the specific gem that is not a fan of Windows), and get productive.