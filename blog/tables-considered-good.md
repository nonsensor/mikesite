---
title: Tables — no longer the devil
date: 2014-11-19
posttype: editorial
tags:
- webdev
- front end
---



A little while back, I linked to [this article](http://colintoh.com/blog/display-table-anti-hero) extolling the virtues of `display: table-cell.` And I wholeheartedly agree. Using table display moves the Holy Grail Layout from hacky and difficult to done in a couple lines of CSS.

One thing the article mentions is source order. The author kind of waves this away as an SEO concern, but I'd argue it's the single biggest issue holding back even the people who aren't skeeved out by the word "table." Source order used to matter little to me; I also thought it was pretty much an SEO issue, or possibly a tweak to page rendering speed at best, but in this day and age? It's easy to move stuff horizontally with floats, but stacked boxes in a mobile layout really need the source order you want to appear on screen. Which, conveniently, is probably the most sensical source order. And if your table layout doesn't support that, you might have created some real headaches for yourself in a responsive page or screen.

Aside from that, I've just started playing with `display:table` in earnest on some sites and I'm experiencing some strange behavior with regard to showing and hiding elements. This is further compounded by shifting breakpoints as you resize the browser.

There's a couple schools of thought on that, both of which I've belonged to:

1. The diligent front end devs who will make sure that they've fixed every little weird issue. This is probably the "right" school to be in.
2. The pragmatic but perhaps somewhat lazy approach says "only designers sit and resize their browsers all day long making sure all the breakpoints work." We're designing for multiple devices and screen sizes, not constantly shifting screen sizes. Probably. And the major layout shift where the bug happens is at a small enough size that you probably won't see it on desktop browser at all, where resizing is possible. Probably.

The thing of responsive layout is that it's an admission we don't *know* all the cases. So knowingly leaving a weird situation in there without making a pretty significant effort to fix it is a disingenuous move. Hopefully I'll make progress on it, and if I do, I'll document it here.
