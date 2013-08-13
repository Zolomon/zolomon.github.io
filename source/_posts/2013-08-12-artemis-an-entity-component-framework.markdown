---
layout: post
title: "Artemis - an Entity Component Framework"
date: 2013-08-12 20:04
comments: true
categories: 
- gamedev 
- components
---

# Artemis

Since a while back I have been reading about entity-component architectures (or, how to utilize data-oriented design) in game development.
What are they? What problems do they solve? These questions are easily answered by watching this:

{% youtube 16ZF9XqkfRY 600 400 %}

They have more great videos at the [Game Engine Architects](http://www.youtube.com/user/GameEngineArchitects) channel on YouTube.

Basically the features are:

* Use compact data structures which utilizes the computer's caches to decrease stalls in the CPU pipeline.
* Higher flexibility for entity management; create different systems that act isolated on a set of entities based on patterns. [This is incredibly powerful and reminds a lot about the functional paradigm]
* Data-oriented; data exist in the form of content and markup files that the game's factories parse to create the in-game entities. Can basically have hot-swap features in-game to allow art users to get instant visual feedback while rendering. If some data file changes, you update the content in-game at the same time. No need for recompilation.

Here are some more links worth checking out:

* http://gamadu.com/artemis/index.html -- the Artemis Framework with ports for most common languages.
* https://github.com/thelinuxlich/artemis_CSharp# -- Very nice C# port which I'm currently using for a roguelike game in XNA.

