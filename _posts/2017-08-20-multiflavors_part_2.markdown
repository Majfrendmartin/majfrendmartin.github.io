---
title: "Multi module and multi flavor project - PART 2"
date: 2018-08-20 23:00:00 +0100
categories: 
  - development
tags: android gradle
---

In my [previous post](https://pawelraciborski.github.io/development/multiflavors_part_1/) I’ve showed how to handle app and library flavors within same dimension. Everything is fine and dandy, but what if we would like to add another dimension to the library. Let's extend our previous example:

<script src="https://gist.github.com/PawelRaciborski/dcd6acb8398e51a196e22369b80956a5.js"/>

*ontop* dimension doesn’t have its counterpart in the app. We have to cover that with in app build gradle:

<script src="https://gist.github.com/PawelRaciborski/872498916aae7372cb7b7dc19b9a40b6.js"/>

First argument is the missing dimension name, and the second is the flavor which will be selected for app build. (You can put more than one here, so you’ll get hierarchy of fallbacks).

It’s also possible to make an exception from missingDimensionStrategy declared in defaultConfig. It can be overridden for a specific flavor. Let's, again, extend script from previous post:

<script src="https://gist.github.com/PawelRaciborski/acbf15c1e27b9b53bb89774be1f00731.js"/>

This last snippet ends this two part post. Complete project can be found on [Github](https://github.com/PawelRaciborski/multiflavours/tree/v0.2).
