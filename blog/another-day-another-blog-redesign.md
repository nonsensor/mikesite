---
title: Another day, another blog redesign
date: 2022-04-13
---





Been thinking about doing this ever since I did the last one. It never quite came out the way I wanted and frankly, the newspaper-ish feel just didn't work. It worked in my head, and it sorta-kinda worked in Figma, and it just didn't translate.

After reading about Utopia and thinking, hey maybe I should do that, I went a little deeper into the rabbit hole of simplicity.

Some notes:
- There was no Figma phase to the "design."
- I did this entirely live by mounting my website with `rclone` and editing live with GEdit (Atom couldn't browse and edit the remote files fast enough).
- There are 157 lines of CSS, un-minified, with a carriage return between each rule. It uses **zero** media queries. There aren't even any columns, so I didn't get the chance to evolve from flexbox to grid.
- I'm using CSS custom properties for the second time in my life, and though it doesn't give me everything I want from the Sass feature set, it's really great to get variables while staying native.
- I didn't quite leave the HTML unchanged, but I probably could've. I've been using almost the same HTML pretty much since I switched to Kirby many years ago.
- Standard posts have a larger first paragraph. This might possibly be inspired by [Lagrange](https://gmi.skyjake.fi/lagrange/), the nicest Gemini client out there.

I suppose I'll enjoy looking at this for a couple weeks and then off we go again, probably with a pendulum swing to complexity. Or maybe I'll just change that yellow to something else to tide me over for a bit.
