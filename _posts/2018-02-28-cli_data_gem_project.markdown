---
layout: post
title:      "CLI Data Gem project "
date:       2018-02-28 21:40:03 +0000
permalink:  cli_data_gem_project
---

Creating your first Gem can be challenging and leaving you unsure where to go, lucky the course material teaches you almost everything you need to know to get started. [Bundler](http://http://bundler.io/v1.16/#getting-started) is a great way to create a structure and is also used to install the required gems you need.  Make sure when your adding gems to perform specific jobs you split them up between what is going to be used for testing/development and those needed to run your app. After you create a file you use as a bridge between other files to communicate(ex. environment.rb), at the top instead of requiring each individual gem, you can use `require "bundler" and
Bundler.require` This will grab all the gems you list in your Gemfile to be used to make your app operate. Remember to keep adding new paths to your environment file anytime you add a new file or folder that is going to be used when running your app.

During this project there were a couple parts that pushed how much time I was originally wanting to spend on it and hopefully as I descripe some of my issues they will prevent someone else from making similar mistakes.  I actually enjoyed and was able to accomplish more with my time on this then any lab before, I think that mostly has to do with writing a program from scratch and having to know the ins and outs of how code ultimately communicates between files and folders. There were  three major areas that turned a two day project into a 5 day project

* Choosing the right website
* Finishing your original idea first
* Refactor at THE END

**Choosing the right website**
This is key when it comes to scraping, there were many websites I used and got about 30 mins in before realizing I was going to have compounding issues in the future. To give an example, there were many websites where I would scrape a particular team (nba teams) from a div and the tag attached to each player was also used for the other information like game time or scores. I spent a lot of time in my code after collecting the team info and then calling the specific spot in the array to get my info. It would work until calling grabbing other teams where some didnt have a time or score and it would return something i didnt want. Moral of this is when grabbing particular data to look around for sites that can offer that information in a clean, direct way as it will save you time and allow you to expand additional information if you need to.

**Finishing your original idea first**
Im sure everyone has this same issue when coding, as you sit there and start writing your program you get an idea to add in another feature or to improve on the amount of information being shown in your app. While this is great and a part of building a better program, you should wait until you finish the basic framework. As I started to make my program I was also adding in new classes and creating new methods on the go. This can get messy and as you change ideas there are some you will no longer use, causing you to go back through again to modify the CLI to make sure it works. As you start to come up with new features you want, write it down and tackle them once your basic program is working. 

**Refactor at the end**
This one is pretty simple but I would try and clean up the code as I was going to try and keep it clean, however as I changed either class methods or wanted new information to be worked in I was constantly trying to reorganize everything. 






