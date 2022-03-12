---
title: How I made my first solo game (for a game jam)
description: "What It's Like to be Reincarnated as a Chinchilla," a game made in 48 hours.
slug: chinchilla-game
date: March 11, 2022
index: 1

---

In this post, I will share the process I had for my 2021 local game jam!

Everything was done remotely by myself in GameMaker Studio 2, which is different from other game jams where I've either been in person or with a team. I chose GameMaker because I was familiar with GML (working on a personal project in it), and is similar to what I'm learning with JavaScript.

I feel like I could have done better to make the gameplay fit to the theme, but I also limited myself to a specific game mechanic I wanted to squeeze in (the shopping cart) before the theme was announced. If I could do something different, I would have done more to the gameplay rather than just the story and visuals. -- Though the visuals got me a 3D printed award for "Best Visuals."

That said, here is what I started with!

<v-img src="blog assets/screenshot1.png" alt="Scripts"></v-img>

I wish I had a video or screenshots of later iterations, but it started as a single cart object that bounced against the walls extremely quickly (and had a cat head, because cat).

Then it became this (smol spritesheet):

<v-img src="blog assets/cart.png" alt="Scripts"></v-img>

Once the jam began, I went to work on ideas that would fit with the theme and stuck with the idea of a becoming a chinchilla in a pet store. Which then became what it is now!

<v-img src="blog assets/screenshot2.png" alt="Scripts"></v-img>

Afterwards, it was a whole lot of level design and pixel art. The music/audio I squeezed in at night and the following morning, and in the final stretch I spent the most time finished the level scripting, UI, and polish.

<v-img src="blog assets/screenshot3.png" alt="Scripts"></v-img>

One reason I love GameMaker is for the room editor. Though it is clunky sometimes, it allows for quickly iterating over level designs intuitively. For complex systems, it also allows room for game objects and scripting to the way rooms and instances work. What I did for this game wasn't too complex, and I had just a few objects such as one for celery collectable, one for the player, one for the doors, etc.

Another reason I use GameMaker for my workflow is the instance creation code:

<v-img src="blog assets/screenshot4.png" alt="Scripts"></v-img>

It allows for modifications to the instance data, which in this case is modifying a single integer value.

In other projects, this can also be used to assign a function (such as how JavaScript allows for storing functions and lightweight objects). This gets into something I did not use for this game, but if I wanted to add dialogue, I would have utilized it.

Ultimately, though it wasn't perfect, I feel like this game jam was a big milestone for me! I hope to continue making games in the future, even if just for fun or in my free time as I continue applying what I learn in programming and development.