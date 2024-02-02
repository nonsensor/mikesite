---
title: Enhancing Kirby with local workflows
date: 2015-09-01
tags:
  - blog
  - kirby
  - CMS
---

I'm enjoying using Kirby to write my blog. It feels more connected to the rest of the site, more in my control, and more "not $5 a month to operate a separate virtual server running Node to have a Ghost blog." But the Kirby Panel, great for spot changes in your content, is not where you want to live every day for blogging. Fortunately, Kirby is a flat-file system that allows users to add content by simply uploading it. So now I'm blogging locally in my favorite Markdown editor and distraction-free writing tool, [Byword](http://bywordapp.com/). There are two parts to making this work.

## Automator
The first half of the solution uses Automator, Mac OS X's super powerful and under-utilized workflow creator. I love it, although it's not always intuitive how to do what you need. Essentially this workflow:

1. Asks for a name that will eventually be the permalink of the Kirby post
2. Creates a folder in my local "blog" folder with that title
3. Copies a text file template into that folder with the name `article.txt` (which is what Kirby needs to associate it with the "article" template
4. Opens that file in Byword, where I can fill it out

Once I write the post, the second part comes into play.

## Dropzone
[Dropzone 3.5](https://aptonic.com/dropzone3/) was recently released, and it's a nice update to a super useful program. Imagine internet (not just web) bookmarks, file actions, and shortcuts, all rolled into one simple place. You can click actions or drag files and folders onto them, depending on what they are. So in order to publish a post, I just take the newly created folder and drag it onto an FTP shortcut I made in Dropzone. Bam, blogged. And I never have to write anything into another web interface again if I don't want to. Thanks to Kirby's self-contained content style, I can put any images for the post into that folder and they'll work as well.

As a bonus, I added the Automator action to Dropzone as well so I can both write and upload the post from Dropzone. It's a handy little tool that's a good buy at 5 bucks. Only downside I've encountered so far is that it can't upload folders to an S3 bucket.
