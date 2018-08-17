---
layout: post
title:      "Sinatra Project"
date:       2018-08-17 19:33:40 +0000
permalink:  sinatra_project
---


My Sinatra project was built to allow people to signup for an account at their favorite bar and be able to order their drinks/close their tabs without needing to have a server there as a middleman. This site works to setup a new user if you dont already have an account and provide you with a couple actions like ordering a drink, view your total bill with each drink you have ordered. There is also a main page that shows everyone who is currently using the app and to be able to see what drinks they have ordered and go to the individual drink description page.

The way this works is by providing a couple associations through Active Record/Sqlit3 that allow a Customer object to have as many drinks and orders as they wise. Once an order is placed a drink id is attached to that order object along with the current customers id. This allows for each person to have their own unique list of drinks they have ordered. Then while giving the drink objects a value in price you can have create a tab that is too be paid off before you leave the bar.

Some of the difficulties were getting the correct associations setup in order to make sure you can see things like, all drinks attached to a customer or each order a customer has made and what was ordered. There is quite a bit more that can be done with this site that can add to the entertainment/info level. A short discription of drink object, customers being able to edit/customize their profile and much more. Also a big part would be adding in new classes that create accounts in which take those orders in as they are placed and providing a system to account for a drink being bought, served then paid for.
