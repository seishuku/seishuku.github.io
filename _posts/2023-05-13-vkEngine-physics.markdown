---
layout: post
title:  "Rigid body simulation in vkEngine"
date:   2023-05-13 10:44:00 -0500
categories: Coding
---

So with the 2D rigid body testing done, I've started moving the code into the [vkEngine](https://github.com/seishuku/vkEngine/commit/e8a18ce3813a1f5626dacab4e88907514490fcd7) codebase.


A little rough at first:
<iframe width="560" height="315" src="https://www.youtube.com/embed/XYz4McQxThk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

But then got the asteroids colliding with each other at least:
<iframe width="560" height="315" src="https://www.youtube.com/embed/MQd_BmzsIzU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

I *think* the weird cyclic action when "exploding" the field is because of the constraints that I'm applying, both velocity limits and area containment, but I'm not really sure.

Currently, it's working fairly well:
<iframe width="560" height="315" src="https://www.youtube.com/embed/aag9D1HVw-A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Asteroid collision with the camera does bump around the camera, but the camera itself doesn't want to move an asteroid unless you mess with the camera mass and approach it slowly, but even then it doesn't always.
Again, WIP and physics are quite difficult to get right, especially getting it to be realistic.