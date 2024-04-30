---
title:  "Flowfields"
date:   2022-02-07
categories: Projects
tags: Pathfinding, AI, Go, Golang
---

As part of my courses, I have studied different pathfinding techniques, but flowfields were not among them. These are used in videogames for crowd's pathfinding as a cheaper alternative to the A* algorithm, so I have implemented a basic demo for this pathfinding technique in a concurrent environment (using Go, as it makes concurrency and synchronization extremely easy).

![alt](/assets/images/flowfields.mp4)


This is a very limited demo as I did it in just a couple of days, and is loosely based on the guides from https://howtorts.github.io/

Its current limitations are:
- There are no physics (velocity, collisions, etc.): every agent moves exactly one cell per movement, based on its current cell neighbours and other agents which may be occupying these cells.

- There are no predictions and look-aheads, since there is a hard constraint which mandates that no two agents can occupy the same cell at any given time.

- The structure is designed for debugging rather than performance and usability:
  - The solution is inherently concurrent but forces each agent to synchronize with a barrier in order to coordinate their movements and render them.
  - Each agent has one flowfield irregardless of other agents who may have the same objective, and also share a shared flowfield for tracking other agents. These two structures should be joined together in order to not duplicate data.


- The obstacle functionality is implemented, but not tested.

The source is available [here](https://github.com/Sondeluz/Flowfields-demo)

