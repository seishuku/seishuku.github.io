---
layout: post
title:  "vkEngine physics update"
date:   2023-05-13 10:44:00 -0500
categories: Coding
---

A little bit of an update to the physics in [vkEngine](https://github.com/seishuku/vkEngine/commit/9480f9aabb4bc04289446e54ec23b0da432d5bae).

I changed out the collision responses to be just reflections about the collision normal, seems to be less janky than the previous elastic I had, but it's also doesn't feel... Natural?
At least now you can push the asteroids around with the camera, though for some reason asteroids colliding with the camera doesn't move the camera... It should, not sure why it doesn't.

Also, what about adding sound for when asteroids collide?
I tried just putting a sound play in the collision, but the problem is that if the asteroids are colliding... Most of the time they'll take multiple frames to fully resolve the collision and it usually ends up with a ton of sound repeats and doesn't sound very good.
However, when it's just a few colliding, it does sound pretty good, but I'm not sure on a good way to fix that... Probably just a silly cooldown counter or something just so it can't play the sound again in X number of checks, but that has it's issues as well.
