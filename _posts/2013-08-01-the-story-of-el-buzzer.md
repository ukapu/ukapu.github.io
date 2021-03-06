---
published: true
layout: post
title: The Buzzer Story
---

Listening to: Kanye West - Hold My Liquor

There have been requests to write a quick post about the Stack Haus Buzzer, so I'm going to detail a little bit about why and how it was made. For visitors to get to the Stack Haus, there are two different gates that one must be buzzed in at. The gate buzzers are typical- they make a voice call to a specific number that they're been given, and when the other end picks up they talk to whoever's at the gate and hit '9' to let them in. (I hope I'm not exposing too many of our top-secret security procedures here.) Usually, the number the buzzer calls is a landline. However, there are no landlines at the Stack Haus, and probably never will be, so something else had to be done. When I arrived here, the system in place was a routing app (powered by Twilio) that made calls to three different cellphones simultaneously, and hung up once one of those phones picked up. This was an issue if someone was away or had turned off their phone, since if a call goes to voicemail it counts as being picked up. So what would happen is that someone would hit the buzzer, it would call a dead phone which would immediately go to voicemail w/o any rings, and neither of the other two phone owners would have a chance to pick up.

The solution was the [Stack Haus Buzzer](https://github.com/FullStackFoundry/StackHausBuzzer). It maintains a list of numbers which can be modified through SMS, and calls each of them in succession whenever it receives a call from either of the gates. To add yourself to the list, all you need to do is text a code to the Twilio number  The buzzer was written in Ruby, using the Twilio API to both receive and make calls, and was hosted on Heroku while also using their built-in PostgreSQL service. It uses the database to store numbers, as well as when they were added and whether or not the number belongs to a person with Admin privileges. What the last one means is that they are able to remove all numbers (except them) from the list through an SMS command. This is nice if someone has forgotten to remove themself from the list. 

Anyhow, this is how it works now. The buzzer works decently well now, and there hasn't been any massive hitches so far. If you've got a buzzer system you're working on, feel free to use it!