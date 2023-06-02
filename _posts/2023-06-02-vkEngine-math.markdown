---
layout: post
title:  "vkEngine math"
date:   2023-06-02 13:47:00 -0500
categories: Coding
---

Current commit to [vkEngine](https://github.com/seishuku/vkEngine/commit/cde663947de1aa53bb25dd2d7922b89b3fa49bec)

I've rewritten the vector code so functions can be chained a little more conveniently (val=Vec3_Addv(a, Vec3_Mulv(b, c)), etc).
HOWEVER, it seems in doing so, I've uncovered an issue when writing to a vector that's located in unaligned allocated memory.

It doesn't crash if the vector is left unaligned, but if I add _declspec(align(16)) to the vector struct typedef,
it will crash on any code that calls a vector function and returns to a vector stored in allocated memory.

So, I need to either just leave the vector types where they are, or modify the zone allocate code to align the size *and* returned address and hope that that does the trick.

Then maybe I can add back in SIMD intrinsics and speed things up a bit, not that it's worth *that* much over basic compiler optimizations, only maybe another 10FPS on the already 300 I get.
