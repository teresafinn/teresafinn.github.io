---
layout: post
title: Hoisting in Javascript
excerpt: "Does hoisting imply there's no encapsulation in JS? Say it ain't so!"
modified:
categories: articles
tags:
image:
  feature:
  credit:
  creditlink:
comments: true
share: true
---

Hoisting - the concept of hoisting and the importance of load order in JavaScript seem to presuppose that code will not be organized into classes. In the Ruby community, people are attentive to encapsulation and good code design. As a newbie to Javascript, I wonder how code organization and encapsulation work? Is executable code written alongside methods/functions without extracting things into logical pieces? What follows is an exploration, mostly for my own benefit, of JavaScript hoisting.

What is hoisting? First a quick recap of vocabulary; I map words to examples to be clear about what I'm talking about:

* Variable assignment: `var myVariable = 5`
* Declared/named function: `function myFunction() { return 'This is myFunction'}` - note the function has a name.
* Anonymous function: `function(y) { return y * y }` - note the function does NOT have a name.
* Function expression: `var x = function myFunction() { return 'This is myFunction'}` OR `var x = function(y) { return y * y }` - note that the functions, either named or unnamed, are being assigned to a variable.

In my own flawed words: hoisting refers to the fact that the JavaScript interpreter first 'hoists' variable assignments and declared functions to the top of its read list. Essentially, it picks these things out and hoists them to the top of the program and then, and only then, proceeds to run the rest of your code. It does NOT hoist function expressions, only variable assignments and declared functions.

But what happens if you've assigned a function to a variable, you wonder? I wondered too. Basically the assignment is stored in memory as `var x = undefined`. Wait but why (A wonderful blog, btw, if you haven't yet been exposed you should immediately pause your JavaScript inquiries and head on over to read about [**How Tesla Will Change the World**](http://waitbutwhy.com/2015/06/how-tesla-will-change-your-life.html)). I'm not sure why the interpreter doesn't just go ahead and point to the value given in the program, but surely there's a great reason. I will explore more and update later.

I imagine a JavaScript spy glass scouring the code seeking out variable assignments and declared functions and then popping them into memory (with no pointer) (or rather with a pointer to undefined). I guess this is just a placeholder for when the assignment actually occurs in the program. So that's hoisting. Okay, cool. (For a much more cogent explanation of vocabulary and great insight into hoisting, see [**here**](https://javascriptweblog.wordpress.com/2010/07/06/function-declarations-vs-function-expressions/).)

So what is hoisting again? It's the offical name we give to the fact that the JavaScript interpreter will mess with the load order you had envisioned, unless you're explicitly aware and are writing your code to account for this behavior. Interesting. I dig rules, especially when I know about them. But. Does this imply that when you write JavaScript you throw everything into one file and that there's no encapsulation or organization or that there's no such thing as well-designed JavaScript code...? Impossible!

I will tackle this befuddling question soon. As soon as I learn enough to answer it. Because surely, *surely* JavaScript code crafters like to be organized and elegant and encapsulated and all that good stuff.
