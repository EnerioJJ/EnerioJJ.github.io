---
layout: post
title:      "How I Learn: Background Learning Tool/Goal"
date:       2019-10-13 16:38:41 -0400
permalink:  how_i_learn_background_learning_tool
---


*{ Please note that some of my words have UK spelling; I was born in the US, but it's just a preference. }*
###### *Also apologies for any formatting errors; the pre-code isn't playing nice!*

It's been a long time since I first started learning Ruby. I think I first tackled the language... oh, I don't know... Five or six years ago? During that time, I was trying to find a language that worked for me making text-only, user interactive games. I've always liked the idea of making games that people can use a CLI to play. That was something that I really wanted to do, but while I was building up to that phase, I was trying to find a language that would, at least, be fun to use as a foundation for text game design. 

I started with Javascript (a language that I have complicated feelings towards), and I somehow moseyed my way over to Ruby. I was amazed by how user-friendly and how direct this language was. The syntax and jargon was incredibly easy for me to understand. Even though I didn't stick with the language and ended up moving to Python (and C#) for my game needs, Ruby stuck with me. Unfortunately, I didn't really have a goal with this language. I couldn't think of a reason to use it. The Internet supplied me with a number of ways that it could be useful, but none of these resonated with me.

And then I was accepted into Flatiron School.

While studying, my mind began racing through the different ways I could use this language. I've been making a list of software/applications I could design. I've been getting ahead of myself and wireframing their designs, haha. (I'll probably have to upload something later and talk about that process). But these are all late game goals. These are all things that I will get to *eventually*, even if that means several months in the future. What is my goal now? 

To design a tabletop game guide.

Let me explain.

Whenever I learn a language, I try to use some type of background learning tool (*pops confetti*) to help me keep on track with what I'm learning. With Python, I wanted to be able to make a turn based text RPG. Even though I'm burnt out on *math*, I actually managed to succeed with that goal where I currently am. With Ruby, I want to be able to make a very basic tabletop RPG game module. 

Take it from me: games are incredibly hard (and fun) to design, and if something is wrong, it will show. If the rules don't make sense, people are confused. If the challenges are unbalanced, people will be upset. You want to make sure that everything flows well and plays nicely together! Designing a game gets more complicated with more elements that you use. (You can even do this with like making a legacy in The Sims, designing a restaurant, designing a website, etc. Having a background tool to learn with helps you learn the important elements of code!)

This is how I summarise everything I've learned from *Variables and Methods* to *Arrays*.


### TABLETOP RPG SET UP


```
ttsetup = ["GM", "Player One", "Player Two", "Player Three", "Player Four"]
game_master = ""
ttplayers = ""

if ttsetup.include?("GM")                                   #include is true, so the condition will continue to execute
    ttplayers = ttsetup[1..-1]                              #array splice
    game_master = ttsetup.shift
end
     
p ttplayers
puts game_master
```


I used a bit of array splicing in this to get the information I needed. Instead of using [1..4] to get from the first index in the array to the last (index 4), I used **-1**. Let's just say that there comes a time where I don't know how long my array is (maybe I have four elements, maybe I have ten), so instead of trying to guess where the very end is, using **-1** allows me to get the last element.

```
def name_your_GM(name="Game Master")                       #method with default argument
     puts "Oh, hey, #{name}! Welcome to the game."
end
 
name_your_GM("Ben")
name_your_GM
```
 
Now, you can also put `return "Oh, hey, #{name}! Welcome to the game."` or just declare it without the return, *but* the interesting thing that I learned through testing was that it won't print both of the `name_your_GM` calls. It will only print the last one. This is something I saw in individual testing in my Repl.it and Ruby IDEs. This might not be the same in the Learn.co IDE. Regardless, in order to prevent any errors, you'll want to put *print, puts,* or *p* to make sure that the calls show.


### NOTING PLAYERS


We've got the basic set up, but now we're going to do a headcount of the players we have. Someone might join in or drop out last second after all!

`ttplayers.size == 4 ? "We can start the game!" : "We need to change some things."`     *#=> "We can start the game!"*
 
This is an incredibly simple way to test if we have the right amount of players, but what if we don't have the right amount? What if there are too many or too little? Well....

```
def game_start
   puts "The game will start in..."

   counter = 10

   while counter > 0
      puts "#{counter}!"
      counter -= 1
      sleep(1)
    end

   return "Let's go!"
end
```

```
if ttplayers.size == 4
   puts "We can start the game!"
   game_start
elsif ttplayers.size < 4
   puts "We need more players..."
else
   puts "We don't have enough room for more players."
end
```



Since we have the perfect amount of players, it's time for our Game Master to kick things into high gear.

