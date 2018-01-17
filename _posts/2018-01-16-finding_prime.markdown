---
layout: post
title:      "Finding Prime"
date:       2018-01-17 02:52:15 +0000
permalink:  finding_prime
---


This was a lab I struggled understanding, it is a problem that sounds easy enough to solve but once you start to write the code it becomes much more difficult. I found it was easier to write the solution working backwards by having any number entered to first be true. Then as it works it way through the method there are if/else statments that if triggered cause the return value to become false. 

As the lab states you want to first identify what a prime number is, its any number greater then 1 that has no positive divisors other then 1 and the number itself. So as you work backwards from every number being true to start, you put in an if statment that causes any number under 2 to return false. 

```
if num < 2
    prime_number = false
```


The next part is doing the else statement, this is going to look at whether the positive number (3 or higher) that has been inputed is only divisible by itself and 1. To do this we use "for i in", this is a lot like using .each to iterate over an object like an array or range and "i" is going to equal each of the numbers in that range from 2 up until it hits num-1. So lets say num = 5, i will run 2,3,4 through the loop. The loop is going to determine if num can be divided evenly by any number that is inbetween 2 and num-1. If it is, then its were going to tell it to return false.

```
for i in 2..num-1
      if num % i==0
        prime_number = false
```

So running this loop if num % i==o comes out to be true we know it is not a prime number, its pretty simple once you understand how it works, but if your like me seeing the code and breaking it down helps a lot with understanding how it works. 

