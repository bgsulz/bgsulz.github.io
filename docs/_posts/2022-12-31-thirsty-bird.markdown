---
layout: post
title:  "Thirsty Bird"
date:   2022-12-31 00:00:00 -0400
categories: 
thumbnail: "/assets/heros/Bird.png"
tag: [games, unity, music]
---
Thirsty Bird is a tiny rhythm game about a symbiotic dance between the raindrops. Use your computer's keyboard to position the bird under the falling raindrops, and feel the rhythm of the skies to help your timing.

A content-complete beta version of the game is playable at the link below.

[Play on itch.io](https://bgsulz.itch.io/bird){: .btn}

@row
<iframe width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/playlists/1640341378&color=%236c6c73&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe>
@column
Thirsty Bird consists of five levels of original music. The style is jaunty and videogamey, featuring sampled instruments and hi-fi synths in blocky arrangements that complement the game's chunky pixel art. You can listen to the music for the first two levels here.

@row
Thirsty Bird will also support custom charts using a simple text syntax. No need for overcomplicated editors with cumbersome copy-pasting -- write charts as fast as you can type, and share them any way you'd like.

```
// set tempo to 77.5 bpm
bpm 77.5

// spawn water in center position, wait two beats
water 4,4; wait 2

// after waiting, we are now at beat 2
// beat 2 will occur exactly at 00:04.71 in the music
downbeat 4.71

// continue spawning and waiting
wait 2
water 1,4; rock 7,4; wait 4
water 4,4; wait 4;
water 7,4; rock 1,4; wait 2
water 7,7; rock 1,1; wait 1
water 7,1; rock 1,7; wait 1

water 4,4; wait 2
wait 0.25; rock 4,1
wait 0.25; rock 4,7; wait 1.5
water 1,7; wait 4

// etc.
```