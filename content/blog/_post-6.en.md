---
title: "redoxide - a free Dota Overlay in Rust"
date: 2026-08-01T13:26:00
toc: true
---
Whenever someone asks me how to get started in programming, I always say the same thing, it even sounds like a worn-out phrase, and I repeat: "Learn with projects", "Make mistakes, read the debug", "Read the documentation". I believe that's the fastest path if you want to see how things work. So I'm proving what I myself say, I'm learning Rust and I decided to build a project that helps me in my daily life.

Vibecoded, obviously, from the backend to the front end, I'm still crawling with Rust, I barely know the basic variables, constants, etc. But seeing how "things work" makes me understand and kind of forces me to learn to read the code, because, in the end, even if the AI writes all the code, I want to know if the flow is as I planned, if there's nothing to be improved, and there's nothing better than learning programming by actually programming (even if it's with Copilot hehe).

## The Project

![redoxide logo?](/images/redoxide.png)

It's an overlay that sits on top of Dota 2 with some panels with visual feedback and benchmarks for the current match. It's like an assistant that tells you if you're performing well inside the match, with data such as 'farming', item 'timming', net worth, etc. They are common metrics that you, as a player, find on sites like Stratz, DotaBuff and OpenDota, common and free metrics.

Today there are overlays that already do this job very well, like Overwolf Overlay and Stratz and others that charge you for it, which I even find unfair, but once at work I heard that "we programmers are like bricklayers, we build other people's houses, but we don't build anything for ourselves". Which makes total sense, because "building other people's houses" is our job and, when you finish the workday, I'm quite sure you don't want to keep working. But then, with this idea that we, as programmers, don't build anything for ourselves, that sucks, right?! So I thought "well then, I'm a programmer and I'm going to build something I need!"

I combined the useful (I need to learn Rust) with the pleasant (an overlay for my little Dota) and I'm developing this project; my goal is to leave it free for the Dota community to use and, who knows, contribute to its evolution. I'm very bad at interface design, so I leave everything in the hands of Copilot and the UI/UX skills I find.

# Screenshots

Some screenshots of redoxide:

## Manager Panel

![Manager](/images/manager.png)
> User's Manager Panel

![Manager with dev tools](/images/manager-dev.png)
> Manager Panel with some tools for testing

## Net Worth Panel

![networth panel](/images/networth-panel.png)
> Panel where the player checks in real time whether they are within the farm timming

## Items Panel

![items panel](/images/items-panel.png)
> Panel with item build suggestions, based on Win Rates

More panels or benchmarks will be added as I find necessary; I'm thinking about some performance tracking by position (Carry, Mid, Off or Supports), but that's just an idea.

I talked and talked, but here's the git link: <https://github.com/redmasters/redoxide-dota>
