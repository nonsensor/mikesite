---
title: Smashing runs down Style Guide tools
date: 2015-04-17
posttype: editorial
tags:
- front end
- style guides
- webdev
---

**UPDATE** It's amazing, looking back 9 years at what was available then. We moved from Stocco to Storybook shortly after and that's become a standard since. But in the meantime there are *so* many more tools, and Figma's Dev Mode just came out of beta a couple days ago.

[Pretty good overview here.](http://www.smashingmagazine.com/2015/04/13/an-in-depth-overview-of-living-style-guide-tools/)

At D&B we started with the PHP-based Style Guide Boilerplate tool but ended up maintaining the most low-impact (but highly manual) system possible. It was a single web page. Comments in the HTML told developers where to grab pieces of markup. Not high-tech, and it required a lot of manual maintenance. But it was easy to keep it looking just like the PSD version.

At PAS I implemented StyleDocco using [Grunt-StyleDocco](https://www.npmjs.com/package/grunt-styledocco). Display leaves a lot to be desired so I ended up diving into the source to modify it. I can now change the template (which is a simple Jade file) and style if necessary.

Why StyleDocco? Short answer: it shows the CSS code. This was important to our developers. StyleDocco creates a new page for every Less file, splits it up by the `<h1>` elements in the comments, and shows those pieces alongside the HTML and samples.
