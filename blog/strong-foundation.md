---
title: If you can't build it all, build a strong foundation
date: 2014-07-04
posttype: editorial
tags:
- webdev
- front end
- design
- UI
---



You've researched, interviewed, put stickies on a wall, flowcharted, wireframed, and designed (mobile first, right?) to a level of total perfection and certainty, and your product or site is going to be great. You nailed it. Then you're asked to QA the beta. Where do you even begin? This thing is just wrecked. You start to wonder if anyone on the dev team even looked at your designs.

Sound familiar?

Desginers and design teams, particularly at large companies, often struggle with their own internal process. But when it comes to working with development teams, things start to break down even more.

## Different worlds

Agile development is a pretty mature process, but it doesn't really account for the more holistic way that product and UX teams tend to work. To a degree, [Lean UX](http://leanuxbook.com) is an effective way for design teams to mirror the agile process and create a tandem workflow, but agile dev versus whole-earth design is only part of the problem.

Communication tools have improved as well: [Invision](http://invisionapp.com), Skitch, and other visually-oriented software takes the back-and-forth out of the realm of cumbersome text documents filled with arrows, screenshots, and vague descriptions.

But at the end of the day, who cares more about the line-height, the spacing, the animation speed, the placement of elements than you, as the designer? No one, because you know the value of what you did. Because you did it for a reason. And what's more, when those visual cues, [microinteractions](http://www.uie.com/brainsparks/topics/micro-interactions/), and precise responsive changes don't come out right, it not only makes for a substandard experience, it reflects poorly on *you*.

So... it's time to own it.

## No mythical creatures needed

This is not more unicorn advocacy (fun fact: in the recruiting world, unicorns are called ["purple squirrels"](http://en.wikipedia.org/wiki/Purple_squirrel)). The answer to all web software design problems is not "turn all designers into expert coders." Not everyone wants to or is capable of doing it all. The chances of finding someone who does it all *really well* are not great. And when you do, over-taxing them with all the work is not going to scale very well. The solution is to empower the team for front-end development.

Whether that means taking advantage of one of the unicorns you *do* have, or hiring a dedicated FED for your design team, it's crucial to build a bridge and stop treating design and FED as two different worlds.

## OK, *not* different worlds then

UX folks know that UX is tied to every discipline and role: Product, design, back end, IT, and even sales. But design teams are responsible for the UI portion, and nothing affects the UI in a web-based experience more than FED.

So what does that actually mean, in a practical sense?

A website or web based product is generally going to have a style guide, even if your shop is lost in the Stone Age. If you're rocking a more modern fashion, you may be using style tiles or a pattern library. But the key here is that your guide can't be a Photoshop file, a list of fonts, and a sprite sheet. It can't be a wiki with PNGs and descriptions. It certainly can't be a piece of paper. It has to live in its ultimate medium: the web. What is a CSS file, after all, but a style guide that actually *works*?

Now, I recognize that every organization is different. With some exceptions, the dedicated FED teams I've worked with tend to be focused on the fun stuff that challenges them in the day to day: data bindings, animations, Gruntfiles (or is it Gulpfiles now?), and other fun scripting. They're worried not just about bridging the gap with you; in these Ajax-heavy times, they have to bridge the gap with the back end as well. And my guess is you're not dealing with strictly HTML/CSS folks — otherwise you wouldn't be having these problems.

Still, it's not good form to run onto the field, jump on the mound, and snatch the glove from the current pitcher. Reach a hand over the wall instead of throwing your designs over it. If your team or theirs is unwilling or unable to put a FED on the design squad, it's your responsibility to make it work some other way. That way is going to mean finding the person most likely to feel some investment in the style control and working with them to build your pattern library or style guide.

## "I don't have that power"

In all likelihood, you actually do. Every company struggles with inter-team relations and workflows. You're not unique. The problem is that Process can rarely fix those breakdowns, and companies are bad at doing things that aren't processes. But *people* are good at communicating. Only communication from the trenches that will solve these issues. It's recognizing that we're all in this together, as the people who are tasked with making the things. It's about people working together instead of blaming each other.

It's definitely not about unicorns.

## Links
Here are some tools for building interactive, live style guides and pattern libraries.

* [Style Guide Boilerplate](http://bjankord.github.io/Style-Guide-Boilerplate/) - We're using a version of this that I modified. It's simple, maintainable, flexible, and it works. It requires PHP, but if you're not up on newfangled stuff like Node then maybe your shop is better equipped for this.
* [Pattern Lab](patternlab.io) - Currently the new hotness. This tool builds everything for you and ensures that all the "atomic" pieces are in place. Also runs on PHP, with a Node version and plenty of other unofficial ports as well.
* [An overview of Pattern Library generators](https://github.com/davidhund/styleguide-generators) - This is a pretty comprehensive list. If you can't find something here, stop being picky or roll your own.
* [Creating Style Guides](http://alistapart.com/article/creating-style-guides) on A List Apart. If you do roll your own, here's what to include.
