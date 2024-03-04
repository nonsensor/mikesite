---
title: How all of this works
date: 2024-03-01
posttype: editorial
tags:
- blog
- wordpress
- CMS
- software
- internet
- kirby
- eleventy
---

A former coworker from the blog era was complaining about WordPress recently and it made me think of the bad old days, as WP was getting further and further from god's light, when I struggled more and more with it. 

## The WordPress problem

I don't like that, as a front-end developer (mostly in the "HTML and CSS" sense, too, not the front end we have today with JavaScript pulling all the weight of applications), I can't really make a WordPress theme. There are ways, such as [Timber](https://upstatement.com/timber/), to make that happen more easily, but that's yet another dependency and more weight added to an already heavy platform.

That's why I initially moved to [Kirby](https://getkirby.com/). I think it's tempting when you've used something like Twig to want to have a templating language layer on top of things, but the truth is that Kirby (and [Processwire](https://processwire.com/), another CMS I've replaced WP sites with) is incredibly simple and doesn't require actual "PHP Coding." We're talking maybe a bit of logic now and again, but in general the functions are handled by an API that is pretty easy to use. Not to mention that both support the idea of defining your types of content, as opposed to having to bolt on yet more plugins to get custom content types and attributes to go with them.

The reason for all this adding on of functionality that resembles Legos a lot less than it looks like a technological shanty town is that *WordPress was built for blogs*. And yet!! Even running a simple blog is now handled more easily by other tools like [Ghost](https://ghost.org/).

## Going static

So here I am, and it's been about a year and a half since I changed engines again, this time to the static generator [Eleventy](https://www.11ty.dev/). One thing you really don't get out of the box with a static site generator is the CMS. But what you *do* get is your Markdown editor of choice. On Mac, that is of course still [Byword](/blog/thanks-byword/), and on Linux it is currently the lovely [Abricotine](https://github.com/brrd/abricotine), but the repo was archived sometime in the fall so we'll see.

So how does it actually work?

## The tools

Here are the requirements in terms of tools and platforms:
1. Eleventy (the Node script that builds a static site from Markdown files)
2. Github (for storing the site files, accessing them from anywhere, and controlling deployment)
3. Netlify with a free plan (for hosting and publishing)

There are a few requirements on the computer side:
1. Node (easily installed via `apt` on Debian or `homebrew` on Mac)
2. Git (or a GUI Git client, which is what I prefer)
3. An editor (even Textedit will do, but why not use a nice one?)

But once you install Node, all the other stuff that's needed is stored in the repository itself. Using the simplest boilerplate and reading the docs for a few minutes was all it took for me to make the simple Nunjucks templates required to make a site run efficiently. It could certainly do even more than a blog, but without a CMS interface I wouldn't give it to a freelance client or anything like that (which is where headless CMSes come in). 

But for the marginally tech-inclined, it's pretty easy. 

## How I do it

So what about actually writing? 

1. Make sure the repo is up to date on the local machine using Git.
2. Create a new text file in your editor of choice.
3. Add the YAML. Posts in Eleventy are configured using YAML at the top of the document, something that is more and more common these days. All the popular static site makers like Gatsby, Jekyll, and Hugo use it, as do flat-file CMSes like Kirby or Grav. It's not too hard to remember the format, but I use Espanso to store it as a shortcut. You could use TextExpander, aText, or whatever you like here, but Espanso works on both Mac and Linux for zero dollars so I'm into it. 
4. Run the Eleventy local server to see your work. It's a quick Node command and you get a really nice lightweight web server that runs your site locally. Every time you save a file, it automatically rebuilds the site and refreshes the browser.
5. Check in and push to Git. That's it. Netlify handles the rest, and in a few seconds your site is ready. It's faster and easier than using FTP to update a static site. Images are the only potential problem as binaries can be slow to upload in Git, but I haven't encountered issues yet. We're talking about images on a website, not extremely large files.

## However

Is any of this really easier than WordPress or Ghost or whatever? I dunno. It's free, I know that. It lets me write in a nice text or Markdown editor, which I honestly feel more than a web interface or tool like MarsEdit. [I've been doing this kind of thing a long time.](/blog/enhancing-kirby-with-local-workflows/) It makes me feel a bit like a wizard. Plus, it hearkens back to an older, more interesting version of the internet that I used to spend time on before it became the engine that powers the most destructive form of capitalism we've probably ever seen. I guess that counts for something. 

Time to go write my next post in Vim.
