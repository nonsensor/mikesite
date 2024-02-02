---
title: Solving the seven sins of CSS
date: 2015-03-11
posttype: editorial
tags:
- CSS
- front end
- webdev
---



Recently, the ReactJS community has set its sights on a new method of building styles into React-based front ends. It comes straight from the source, Facebook. Here's the deck.

<script async class="speakerdeck-embed" data-id="2e15908049bb013230960224c1b4b8bd" data-ratio="1.33333333333333" src="//speakerdeck.com/assets/embed.js"></script>

I think this presentation makes a lot of sense to a lot of developers who've begun to think in the component-based (and honestly very sensible) React methodology. But there are a lot of strange justifications and a path paved with over-engineering that leads to vjeux's ultimate solution.

Warning: This is long.

---

## The "Problems"

First, here are the problems that vjeux outlines. I'm not here to provide better solutions for them, but I will say that in many cases, they're not really problems at all.

### 1. Global Namespace
Firstly, I think this is key to illustrating why a developer of vjeux's caliber can have a great thought process but miss the boat to some degree on CSS. He calls a class a "global variable." This seems at first like a matter of introducing programming semantics into the conversation so we all know what we're talking about, but I think it's conflating what a *class* and a *variable* actually are. The word itself indicates that the value of a variable can change — if anything, a CSS class is a constant. It's simply a pointer or reference. If you prefer, a class or ID selector is a set of rules more akin to a function (or, in OO, a *class*... probably no coincidence there).

But getting away from a concept I honestly feel somewhat inadequately equipped to really talk about at length, the "namespace" issue itself is the first of these that isn't really an issue. A class living on its own, even one attached to an element (e.g., `div.myclass`), does inhabit a "global" namespace in the sense that you can use that class anywhere with no limitations. Only good practice will limit you. But writing self-contained rules is not incredibly hard, is it? Take this piece of LESS (roughly identical in SCSS):

```css
.specific-container {
  input.super-specific-input {
    /* style rules */
  }
  label.super-specific-label {
    /* style rules */
  }
}
```
In the sense that `.specific-container` is available to use and abuse anywhere, it is a "global" element. But that class in itself becomes an effective namespace for anything within it. And a few simple naming conventions can take that further.

I can barely think straight to comment on these (literally) backwards extensions that the Facebook team apparently wrote before arriving at the conclusion that they should abandon CSS altogether.

### 2. Dependencies
I'm not entirely sure I understood this section, mostly because the expectations of CSS working like a build process (i.e., errors should cause everything to break) is such a foreign concept to me.

Maintainability and monitoring the Cascade used to be a huge issue with CSS. This is something that preprocessors have solved incredibly well, even though they don't change many fundamental aspects of CSS. That includes the Cascade itself, but one of Less's early counterarguments was that the ability to write such modular CSS discourage "proper" or *cascading* use of styles. I'm not exactly pedantic on that myself, but if one were so inclined to write completely modular Less/Sass with no globally-impacting styles and no large-scale cascading, it's not very hard to do. Basically the above example, repeated numerous times as separate files and associated with each module or UI component, *becomes* a set of dependencies. These are easily managed by Less/Sass imports.

### 3. Dead Code Elimination
Near as I can tell, what they're referring to as "dead code elimination" is a product of their own solution. I can't really speak to this.

What I can say is that poorly-maintained, long-running, legacy CSS (the old way, without the concatenation made possible from preprocessors) is a problem for a lot of people. This is not a fault of the language itself. Less/Sass certainly make it easier.

### 4. Minification
Maybe someone can help me here, but I'm confused about this one — the old, extended-CSS solution let Facebook's developers use incredibly weird, non-semantic, but very short class names in order to save a couple bytes. It's bizarre but has its logic. So how does programmatically replacing a token with a long list of inline styles — which are maintained as a single component but echoed into a page once for every instance — save bytes? Not sure. If semantic class selectors is a problem of byte size, that's fine, but I don't think it's one that huge, redundant inline styles can solve.

### 5. Sharing Constants
What's the old quote? There are two hard things in computer science: cache invalidation and naming things. Making your stuff sync up between content, presentation, and behavior is a problem old as the hills, but most teams don't have the specific problem in this deck because they're not working with this weird system.

What vjeux shows here is a worst-of-both-worlds scenario where style has been mixed into behavior, but not all the way. I would argue that yes, in fact, his completely inline solution is a better answer than the hodgepodge here.

```js
var buttonPadding = 5;
```

Reading that physically hurt me. He says "unfortunately there are many real world use cases where you need to do it." Not sure I buy that. If you really, *really* feel this need, there are tools for your Grunt or Gulp file that will transform a list of Less/Sass variables into Javascript at build time and thus keep the values synced automatically.

Upon reading the solution they developed, I got pretty confused at "CSS Variables."

### 6. Non-deterministic Resolution
This is another case of holding CSS to the same standards of behavior as a logical programming language, which it is not. The "linear" flow of later rules overriding earlier ones is always something that programmers struggle with because they can't organize things according to how they like; **they must organize according to how the web browser is going to read the document**.

Writing with the modular, "namespaced" blocks of Less/Sass eases these problems in two ways: one, confining the rules to their own pocket of markup will keep them from affecting anything else in the application, and two, the ease of auditing the styles will prevent unexpected cascades.

### 7. Breaking Isolation
I feel sad for the team at Facebook who've been burned by a poor understanding and even poorer practices of CSS writing. Overriding in the way shown in the example is unfortunate. But imagining myself as a designer in that organization, forced to think in an upside down way about my CSS, it kinda feels like it's no wonder the designers reach for non-ideal solutions as long as they *work*.

---

## My Problems with the Solution

I can certainly see the appeal of just styling within the component as Javascript. The author does fall into a pattern that is common among devs (I've done it too): a post-hoc justification.

> Second, style is actually a much better name than class. You want to "style" the element, not "class" it.

Let's not bring the semantics into it — I get that the actual english *words* make more sense, but we've all agreed on what that word means in the context of markup. This is a side point though.

#### 1. Redundant bytes and information
Whether you're talking in terms of human readability or the space taken on disk/downloaded over the internet, I have to question whether multiple references to a single CSS class:

```css
.btnClass {
  background: #333;
  border-radius: 2px;
  color: #fff;
}
```

is not preferable to

```html
<button style="background:#333;border-radius:2px;color:#fff">One button</button>
```

repeated over and over throughout the application. And here of course I'm using a very simple example; most real-world CSS rules are going to be *significantly larger*. This is one of those questions that I assume has been empirically answered, but there isn't a lot of usage of this method going around yet, so I don't know.

### 2. Separation of Concerns
I get the very real benefits in React of mixing concerns while separating physical application pieces. Everything associated with this piece (structure, style, behavior) is in one place, so I know exactly what needs to be done in order to make a change to that piece.

But part of the benefit of the classic "separation of concerns" philosophy is the ability to take a holistic look at the styles. For all the supposed solutions with regard to maintenance and dead code elimination, I'm afraid this has created many more potential ones. Obviously, this is to some degree going to be dependent on how a React application is structured, but components can't truly share stylistic elements, even if they have individual styles in common. So the ability to change that stylistic element from a central place is now lost.

The best we can really do with this method is reference a central variable, or possibly (I'm not even sure about this) something like a mixin. Like any of the CSS-based solutions that vjeux writes off as non-enforceable, this requires good practice.

### 3. Separation of Work
vjeux himself admits that part of the motivation for Facebook's crazed bolting on to CSS is due to having a large team of developers working on highly focused portions of code, most with limited expertise in front end. This is, let's be frank, not an uncommon problem but it is a specific one.

Though tools like KSS have been around for a while, style-guide-based development is just now coming into its own. Mailchimp, Starbucks, Lonely Planet and others have made huge and very public strides in building component libraries that developers can then reference and drop into new pages.

The benefits are easy to see: a streamlined design process, easy enforcement of standards, and a refocused approach that encourages solving problems with the same design patterns where possible.

With all styles inside the React components, control over front end is not only not handled holistically, it is handled entirely by developers who may or may not have much expertise with browser discrepancies, best practices, and all the other myriad of things that CSS writers actually focus their time on.

### 4. Missing Features
Generated content and other pseudo-class selectors are pretty much not available here. Is it overkill to impose a hover state just for a color? Perhaps not with React, whose bread and butter is state change.

And what about media queries? This is beyond unfortunate:

![Not the best Responsive Design](/img/mediaqueries.png)

## Toward a better way
These are all fairly new issues. vjeux's still giving this presentation, and it only went online in November. React developers are still discovering the process and trying it on. The argument on Hacker News is still somewhat active.

My problem is not with upending dominant paradigms. It's not with trying to find new ways of styling. But ditching most of the primary benefits of CSS/Less/Sass and justifying that with arguments based on some inaccurate assumptions is a paradigm shift that doesn't quite feel necessary.
