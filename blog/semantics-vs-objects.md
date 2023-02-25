---
title: Semantics vs Objects and other scary CSS animals
date: 2016-05-18
posttype: editorial
tags:
- CSS
- front end
---

I suppose it was only a matter of time. The backlash always appears. It's a pretty old argument to be honest, the idea of getting "back to basics" or "using the web as it was meant to be used." But the reason that front end devs have gotten a bit away from [these kinds of methods of styling](http://alistapart.com/article/meaningful-css-style-like-you-mean-it) is that it doesn't support everything that everyone wants to do anymore. 

I'd still say that if you're making a website — even if you're working with atomic or styleguide-driven design — you're better off taking advantage of HTML elements, ARIA roles, and the cascade to style your site. But in the world of applications where structure is arbitrary and markup is not necessarily the most readable thing in the world (and guess what, this is often out of our hands), being reusable and "bulletproof" is more important to a lot of front end folks.

It's funny because this debate appears just as I'm finally considering adopting BEM in a project. I love — and need— the idea of a self-contained piece of UI that I can drop anywhere. At its best, this is front-end methodology as UX improvement, because the consistency of those pieces of UI helps the overall experience. Even without that benefit, it aids in speed of dev. Embarrassingly, perhaps the main reason that I gravitated toward BEM is that I'm sick of figuring out what to call things as I place HTML elements on a page.