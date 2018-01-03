---
layout: post
title:      "Truly Understanding Concepts Taught"
date:       2018-01-03 18:18:16 +0000
permalink:  truly_understanding_concepts_taught
---


One of the more difficult things I struggle with doing in this program is actually understanding the use of each concept and method that are taught in the labs. I know there are people out there like me who have trouble looking at a lesson and being able to apply it outside the lesson. This is something I learned in college to deal with and hopefully someone reading this blog will be able  apply my way of learning to their own life and make learning that much easier. As I have been going through the program I have times where im spending way to much time on one problem trying to get it to work and to be honest I retry the same code over and over trying to just tweak it to work which normally doesnt work but even if it did I would not understand why. What I have started to do, is if I get stuck for more then 10 mins on one problem, I have been going to this site http://ruby-doc.com/docs/ProgrammingRuby/ to learn methods that achieve a similar result. Knowing multiple ways to solve one problem helps you identify why the current code doesnt work. 

As an example I was recently stuck on "conference_badges.rd" I had an issue with interpolating both the name of each person as well as assigning a room number. The lab called for me to use .each along with some other methods but I was having trouble getting the room number that I assigned to the first person to increase by 1 everyime a new name from the array was put through. I went onto the website and looked up .each and sure enough there was another method right below it that used .each_index. Which instead of returning the element in the array it returns its position within the array. This was exactly what I needed and with a little bit of research found you could use .each_with_index to interpolate both the name as well as their position in the array (aka room number assigned). 

While most of the time I use what the lesson has given me to complete the lab (a lot of tests require this), however learning different ways to accomplish the same goal actually help me understand the labs. I think because im trying to apply a completely different solution it lets me see the issue from a different angle.
