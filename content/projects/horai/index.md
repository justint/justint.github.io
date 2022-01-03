+++
title = "Horai"
date = 2020-07-26

[taxonomies]
categories = ["game"]

[extra]
featured_image = "img.png"
+++
A survival game to keep a flower alive by changing the seasons.
<!-- more -->
<p style="text-align: center; font-weight: bold"><a href="https://jaredr122.itch.io/horai">🎮 Play on itch.io</a></p>

> Change the season with SPACEBAR. Keep the flower alive. Too hot or too cold, the flower will die. The animals prefer certain conditions, but you'll have to figure those out as you play!


My first ever game completed in a game jam, built with [Godot](https://godotengine.org/)! I developed this with a friend for the [My First Game Jam: Summer 2020](https://itch.io/jam/my-first-game-jam-summer-2020/rate/711724). I was responsible for the particle systems (rain, leaves, snow), health & temperature system, and music. 

At the time we developed Horai, the world was deep into the COVID-19 Fun Times™, and we had a formidable need to unleash some creative energy. We tossed a few game engine ideas on the wall, but settled with using Godot for its shallow learning curve, easy file management, and strong community support. It was a great learning experience, and we were satisfied enough with Godot to make [another game with it later that year](@/projects/pitter-pat/index.md)!

Here's some in-depth juiciness of what I worked on:

# Graphics

Besides the [particle system](#particle-system) mentioned below, I also added the season transition effect:

<video src="seasonchange.mp4" controls></video>

This was a direct implementation of DDRKirby's wicked cool shader-based transitions[^1]. All the rest of the game's beautiful pixel art was done by my super talented teammate!

## Particle System

Just after we first added our flower sprite into our forest, we realized that the environment felt dead, too static. I tinkered around with Godot's [Particle System](https://docs.godotengine.org/en/stable/tutorials/2d/particle_systems_2d.html) and managed to get some nice seasonal weather added:

<video src="rain.mp4" controls></video>

<video src="leaves.mp4" controls></video>

<video src="snow.mp4" controls></video>

# Mechanics

## Health & Temperature System

In Horai, the goal is to keep the flower alive as long as possible. I implemented a simple numerical health system (`9 = `full health, `0 = ` dead) on the flower, and a global temperature variable in the game (`var temperature = 60`). I also defined a "Goldilocks range", where if the temperature ever dipped below or above the range, there'd be a certain (small) chance that the flower would take damage.

Each season (`enum SEASONS {SPRING, SUMMER, FALL, WINTER}`) had a defined influencing behavior on the temperature of either increasing to a maximum, decreasing to a minimum, or adjusting to a median temperature. 

# Music

During development, we curated a playlist to help set the tone and mood of our game:

<iframe src="https://open.spotify.com/embed/playlist/03FQSmm6pXmMz6PqTo5jOE?theme=0" width="75%" height="300" style="display: block; margin: auto" frameBorder="0" allowtransparency="true" allow="encrypted-media"></iframe>

## Soundtrack

Feeling inspired by our playlist, I developed a soundtrack for the game!

<div style="width: 70%; margin: auto; padding: 10px 0">
Spring: <audio src="spring.mp3" preload="metadata" controls loop style="width:80%; float: right"></audio>

Summer: <audio src="summer.mp3" preload="metadata" controls loop style="width:80%; float: right"></audio>

Fall: <audio src="fall.mp3" preload="metadata" controls loop style="width:80%; float: right"></audio>

Winter: <audio src="winter.mp3" preload="metadata" controls loop style="width:80%; float: right"></audio>
</div>

The season's themes were produced in Ableton with Serum, and written with intentionally similar themes to bring a sense of cohesion across the seasons.

# Closing Thoughts

I'm very proud of what we accomplished in the week of development, in the limited hours outside our regular jobs! Most of our time consisted of poring over Godot's documentation and learning rapidly while tinkering -- by the end we were excited to have _something_ playable, but even more excited to begin building bigger and better things with the engine.

Here are some of my learned lessons: 

- _Lock down your idea early, and leave time for playtesting._ Avoid what we did of spending the first half of our game jam coming to a decision (oops... lol)

- _Identify your priorities and keep your focus._ I found myself getting distracted by all the nifty features within Godot, especially those relating to graphics. I also probably spent more time trying to deliver the aesthetics for the game than the gameplay itself. 
  
  For future game jams, I've learned I should prototype and iterate more swiftly, and try not to get too caught up in QC'ing/bug-fixing while developing. Your time in a game jam is precious!

- _Seriously, leave time for playtesting!_

[^1]: [https://ddrkirby.com/articles/shader-based-transitions/shader-based-transitions.html](https://ddrkirby.com/articles/shader-based-transitions/shader-based-transitions.html)