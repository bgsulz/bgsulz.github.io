---
layout: post
title: "Lyrically"
subtitle: "Lyric excerpt daily guesser"
thumbnail: "/assets/heros/Lyrically.png"
tags: [project, design]
permalink: /lyrically/
startdate: "2024-08-01 00:00:00"
---
Lyrically is a daily guesser game: guess a song from lyric fragments. It has daily puzzles and an archive where you can play all past puzzles.

[Play now](https://lyrics-guessing-game.web.app){: .btn}

This is the first of several daily guesser games I plan to create; it's a proof of concept partially intended for determining a dead-simple "tech stack" (if you can call it that) to enable easy puzzle design and rapid iterative publishing.

## How does it work?

Like [Auther,]({% post_url /projects/2024-09-01-auther %}) the frontend of Lyrically is built with Flutter. Its source code is [on GitHub here.](https://github.com/bgsulz/Lyrically)

The backend of Lyrically is unconventional. It's worth noting that I'm working on Lyrically with my father, a veritable human encyclopedia of lyrics knowledge. We collaborated on the design of the game, and we're working together on the daily puzzles as well.

My goal was to make it ***as easy as possible*** for my dad and me to update the game with new puzzles. The solution: Lyrically puzzles are stored in... a Google Sheet. I set up a Google Apps Script that updates a Firestore database with all new information from the Google Sheet at the click of a button.

For the convenience of having a single "dashboard" for managing Lyrically, the site is also hosted via Firebase. The result: collaborators can operate within the familiar interface of a spreadsheet, so managing and appending to the game's data is trivially easy. I intend to reuse this exact paradigm in future daily guesser projects.