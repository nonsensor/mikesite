---
title: Better static sites with Jade
date: 2014-08-05
posttype: editorial
tags:
- front end
- webdev
---

**UPDATE:** I haven't used it in a while but in theory I really still like ~~Jade~~ Pug.

If, like me, you've been riding the current wave of preprocessors and static site generators, you're probably overwhelmed by the choices out there. As with musical tools, I tried to [take my own advice](/2014/04/16/the-enemy-of-done/) and pick one thing to stick to for a while, see how it goes. I happened to pick a less-popular, less-mature tool with less documentation and material out there than any other. But it's not based in Ruby, and that should make Alex happy.

Jade was created by a 22-year-old CS undergraduate in England, and it's a super cool little pseudo-language for templates, written in Node. Unlike Ghost, which powers this blog, you don't need to get Node running on a web server to make sites with it, which can restrict your choice of web hosts. On the contrary, you run Node on your local box and generate a static site with the Jade processor, then host that bad boy pretty much anywhere.

Here's a little bit about Jade, and if you've used templating engines before you may find it to be pretty familiar. If not, then it's a really good starter language.

## Basic Syntax

If I had to pick a central principle of Jade's syntax, it'd be the indention-awareness. Yes, it's written in Javascript, but you won't see brackets and semicolons everywhere (which is something I think Sass has over LESS). Just indent the next line and you're nesting html or logic.

```pug
body
  .container
    h1.pagetitle Page Title
    p#opening-paragraph This is some text.
```

Pretty simple, right? `div` is an implied tag, and the `#` and `.` do what you might expect if you passed CSS 101. Here's the output:

```html
<body>
  <div class="container">
    <h1 class="pagetitle">Page Title</h1>
    <p id="opening-paragraph">This is some text.</p>
  </div>
</body>
```

A benefit here is that keeping tags properly nested and closed — which can be a bear when you're dealing with templates — becomes a lot easier.

Attributes are written as arguments, so this

```pug
a(href="/blog/",data-custom="val") Blog Link
```
produces

```html
<a href="/blog/" data-custom="val">Blog Link</a>
```

Aside from a few idiosyncracies and some details, that's totally it for markup. I can't speak for all editors, but the always-wonderful Sublime Text does have syntax highlighting schemes for Jade to make life a little easier.

## Variables

Variables are defined pretty easily — no need to set up a special block of Javascript or anything, just define it with a dash and put spaces around the `=`.

```pug
  -var dogname = "Rufus"
```

There are a couple ways to use variables. THe most basic is to put an `=` immediately (no spaces) after an element:

```pug
h2= dogname
```

This will produce `<h2>Rufus</h2>`, which is a pretty great dog name you don't hear nearly often enough. But sometimes things aren't that simple, and you need to get the variable into a string. If you know you want to produce `<a href="Rufus.html">Rufus</a>`, you can use a pound and curly bracket syntax.

```pug
a(href="#{dogname}".html)= dogname
```

This combination of the two types of variable output gives us what we want.

## Mixins and Includes

Being tired of typing opening and closing carats is a pretty good reason to use Jade to begin with, but there's a lot more power in it than saved keystrokes and easy tag closing. Like CSS preprocessors, it gives you mixins, and like server-side languages, it provides for includes.

Includes are so self-explanatory they're barely worth mentioning, but I'll say this: remember your indentation when you call the include. You want to make sure your HTML structure stays intact.

Mixins are reusable blocks of markup or code that can take arguments. These can be used to absolutely destroy repetitive tasks. If you're in any way familiar with programming, think of a mixin as a function. Because that's what it is.

The following

```pug
mixin gal_image(imgurl,caption)
  li
    img(src="images/#{imgurl}")
    p= caption
```

Looks a little tricky, but let's break it down.  First you define a mixin using the unsurprising keyword "mixin." You can add arguments as well — and you will likely need to.

You can output the arguments in both of the same ways you'd use explicitly defined variables. To use the mixin, just add a `+` and call it, putting the arguments in parentheses much like a javascript function. Here's an example usage for the above.

```pug
+gal_image("my_image.png","This is an image")
```

which produces

```html
<li>
  <img src="images/my_image.png">
  <p>This is an image</p>
</li>
```
Not bad, right? As in this example, mixins can make short work of repetitive elements like photo gallery or portfolio images.

## Extends

As with many template languages like Smarty or Django, Jade utilizes the concept of child templates and *Extends* to make files more efficient and manageable. For instance, a website could have a `page` template and a `company-info` page template that's based on it. Extends can go as many levels deep as you like, but a typical case for a static site might be 3 levels: *base → page type → individual page.*

In order to take advantage of them, just add `extends` with the URL to the base template at the beginning of your file. If you want them to really work for you, you'll want to use *Blocks*.

## Blocks

If you've never used a templating system that features them, Blocks aren't immediately intuitive. But they're hugely powerful, and they're what makes Extends really work. In any given template, think of it this way: includes are static markup, but a block is something that could be variable from page to page.

```pug
include includes/header
body
  .content
    block pagecontent
include includes/footer
```

Here, the header and footer are includes because they're the same throughout the site. But to get a variable piece of markup or content in the `.content` div, we use a Block.

Now, on each page, tell Jade that we're extending the `base.jade` file, and reference the same `pagecontent` block:

```pug
extends base

block pagecontent
  h2 My awesome title
  p Hi I'm writing content! It's king, I hear.
```

Not rocket surgery. You can also define a default in the base template, so that in the event a given page doesn't have that block you can always fall back.

## Getting it to Run

So how does this stuff work? I mentioned that it's not a back end language, so you're not going to run it on the server. It's pre-compiled into static files. Jade, like other Node-based tools, can be compiled in a number of ways. I'm not planning on getting too into that, but here are a few:

* Node on the command line. This is the most basic. You can just compile a directory of Jade files into HTML, or have Node "watch" the directory and compile the files as you save them.
* [Grunt](http://gruntjs.com/), which can run lots of other Node-based things at the same time with a single command in the terminal, and then get packaged for a deployment environment that works the same as your development one. Unfortunately, Grunt requires a lot of up-front setup to make that single command work. There are resources out there.
* [CodeKit for Mac](http://incident57.com/) (this app is really what got me into Jade. It's a bit costly but fun and also works with plenty of other pre-compiling tools)

Next I'll outline how I put together a portfolio site using Jade and LESS. Hopefully this was helpful.
