---
title: (A series of grunting noises)
date: 2014-10-09
posttype: editorial
tags:
- webdev
- front end
---



I've finally taken my first step into the wide world of yesterday's favorite web technology with a new understanding of Grunt. **UPDATE: It wasn't long before I moved to Gulp. Welp.**

It's par for the course that designers and front end devs are trendy, fad-prone folks with their eye to the future and an almost obsessive-compulsive desire to find the "perfect" set of tools or processes. And by now, many (especially the ones prone to blog posts) have moved past Grunt to another Javascript/Node-based system called Gulp.

I'm not there.

I love being hip and with the times too — I have a Ghost blog. But having just discovered enough information about Grunt from ebooks, coworkers, and Stack Overflow threads to be dangerous, I'm not about to move on just yet. And now that I "get it," I have to say that maybe it *is* kind of the "perfect" tool.

## What will make Grunt resilient in the long run?

The "perfection" of Grunt is not about its extreme levels of functionality, nor its user-friendliness (lol). It's the flexibility. Grunt serves that obsessive-compulsive tool-design side of front end with a lot of plugins and an easy way to write more. If you're a FED and you really need something that isn't in the Node Package Manager (NPM) repository, then maybe you should consider taking your skills to the node-module-writing level.

It's also super portable, which makes creating an environment a snap — just install Node, and you can run Grunt-powered sites and apps. I've heard opposing arguments on whether to put your Node modules for an app or site into Git, but right now we're not. Any new environment just needs to run `npm install` and they're up and running. It's literally that easy.

## What are we doing with it?

Currently I'm working on a static prototype with bootstrap (LESS version), JQuery, and a few charting libraries. Grunt moves static files from a `src` to `dist` directory, minifies Javascript, compiles LESS files and Jade templates, and runs [Browsersync](http://www.browsersync.io/) for live reloading and injection. When we're all synced up, it also deploys to Amazon S3 for the stakeholders to view live.

This is a relatively simple setup for Grunt, which can do all kinds of more Node apps and complex whosamawhatsits. But it's the right tool for the job when compared to something like Preproc or CodeKit which, don't get me wrong, are nice apps.

For instance, I nailed down the file structure early and defined it in the Jade compiler. Now every new Jade template added automatically compiles to an HTML file in the right structure. CodeKit requires me to define the path of every new template.

Grunt also lets you create multiple setups. For instance, in development, the watcher and compiler might not minify the final Javascript and CSS so they're more easily debugged in the browser. But on deploy, minify it all. And this is all a one-time setup.

## Downsides

That one-time setup is pretty much Grunt's big downside. The syntax is a bit arcane to me, not quite resembling any normal Javascript or JSON files. Installing packages is a breeze with NPM, but actually setting up the tasks and getting them to do what you want can be a many-hour process.

Now, is that worth the flexibility and other advantages it offers over simpler GUI compiler applications? Depends on your use case, I'd guess. For us, it's really fantastic. I still use CodeKit on some other sites, and I'm sure the daunting setup process will keep me away a few times that I might prefer using Grunt.

But overall, it's been fun to learn and satisfying to set up a workflow exactly how I want. That might make me a fad-chasing Kool-Aid drinker but I'm happy to never struggle with my tools not doing what I want.
