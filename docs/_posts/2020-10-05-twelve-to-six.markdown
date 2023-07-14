---
layout: post
title:  "12-to-6 Shift"
subtitle:  "Puzzle-programming game; top 2% in Ludum Dare 47"
date:   2020-10-05 00:00:00 -0400
categories: 
thumbnail: "/assets/heros/12 to 6.png"
tag: andr
---
For Ludum Dare 47 -- theme "Stuck in a Loop" -- I was the sole artist and lead programmer and designer on the our team of three. Using Unity as our game engine and Affinity Designer for artwork, we created 12-to-6 Shift, a programming puzzle game about rigging a friendly robot to do your pizza deliveries for you.

[Play on itch.io](https://bgsulz.itch.io/12-to-6-shift){: .btn}

To facilitate the game's interactive programming, I coded a real-time "interpreter" that dynamically responds and adapts as instructions are added and removed. 

Due to Ludum Dare's tight 72-hour time limit, I had to ensure that the system was modular enough to add or modify instructions last-minute. Lo and behold, our team's level designer requested a new "Step" instruction -- one that moves the robot only one tile in its current direction -- and I implemented it into the game's programming system within minutes.

The game's art had to be similarly modular. I built a large and comprehensive level tileset, allowing our designers to rapidly iterate upon their levels with no need to switch out placeholder art after the fact.

Even the decorative houses are fully modular.

@row
![Modular Roads](/assets/twelvetosix/Modular%20Roads.png)
@column
![Modular Houses](/assets/twelvetosix/Modular%20Houses.png)

@row
The game was ranked 48th overall, placing it in the top 2% of submissions.