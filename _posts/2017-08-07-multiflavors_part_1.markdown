---
title:  "Multi module and multi flavor project - PART 1"
date:   2018-08-07 00:23:00 +0100
categories: 
  - development
tags: android gradle
---

In the latest project I’ve started working on I’ve faced problem. Project was divided into multiple modules (Android app, Wear app and library). Both apps have multiple flavors with multiple dimensions (and by multiple I mean a LOT of them). This makes me wondering what is a proper way to handle multiple flavors in multiple modules in single project.

But let start from the beginning. 

We have an app build.gradle with 5 flavors in two dimensions:

<script src="https://gist.github.com/PawelRaciborski/e559681bd8ad8c51f3abcbfbbd25a1fb.js"></script>

In a standard case you, my dear reader, would add local dependency like this:

<script src="https://gist.github.com/PawelRaciborski/04638ec48c1b761bfded386c3b297f68.js"></script>

Situation is not changing if all library dimensions has their counterpart in the app, eg. if we have library flavors:

<script src="https://gist.github.com/PawelRaciborski/3b78c0681bac0f6323fb047aeac71499.js"></script>

everything will work fine.

Things get more interesting, if we’ll add extra flavor to our app:

<script src="https://gist.github.com/PawelRaciborski/e4f4aeeb11d3258ab523a3465f55ff25.js"></script>

Gradle doesn’t know what to do with raspberries, so we needs to define fallback strategy:

<script src="https://gist.github.com/PawelRaciborski/ca816fe62ad3baabcba5ad3104aaf192.js"></script>

Complete code for this post can be found [HERE](https://github.com/PawelRaciborski/multiflavours/tree/v0.1). In my next post I’ll describe how to handle situation when library has its own dimensions subset. 