---
title: Inline validation considered harmful
date: 2017-06-28
posttype: editorial
tags:
    - design
    - UX
    - front end
    - javascript
---


Just kidding, [this article](https://medium.com/simple-human/inline-validation-is-problematic-399dd01d436f) didn't really use that word. And rather than an alarmist view, this is a fairly measured take. However, most of the arguments are actually against *realtime* (onblur) validation, not *inline* validation. 

I spent two years dealing with some serious problems that were born entirely out of the fact that an application used realtime+inline validation. And that was primarily in a series of wizard-like dialogs, which really didn't make any sense (the pattern of "disable the continue button until validation is cleared" would've worked well).

Our problems included:
* forms that didn't require a certain order to filling them out, but validation that did
* false positives triggered by mouse actions that left users in an unresolvable state if they clicked "wrong"
* field groups often in a false-positive state (point #4 in the article)

This isn't the same as saying that *per-field* validation is wrong, and I still strongly believe in that, but this article has a lot of solid points.