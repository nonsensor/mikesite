---
title: Harrison Mixbus first impressions
date: 2014-07-03
posttype: editorial
tags:
- audio engineering
- software
---



I've never worked on an analog console. Sure, I've sat with someone and suggested technical and creative engineering decisions while they operated, but the UI paradigm of a console is only useful to me because I've used desktop mixers, and because pretty much all DAWs use some form of this paradigm. I don't have any allegiance to the old ways or the "sound" factor that usually consists of a bunch of vague assertions that analog summing is better (usually coupled with assertions that tape is better as well).

But what I do have is that drive to find the better workflow, the fastest way to creativity mixed with the ability to generate results. I also can't pass by a deal. For a $20 "no brainer" deal, it was certainly worth trying out Harrison Mixbus, even though Pro Tools is the standard and is a generally satisfying experience once you learn it.

The origins of Mixbus are interesting enough on their own: the project was born from an open source Linux DAW called [Ardour](https://ardour.org/). The Harrison console company, known for their super high end consoles used on a huge amount of popular records, used the existing open codebase as a skeleton that they fleshed out with their own EQ, compression/leveling, saturation, and summing algorithms.

## Out of the box

Installing is a minor pain due to the requirement of a JACK installation, and subsequent restart. JACK is a system-level audio router that's somewhere between Soundflower and Propellerheads' ReWire. Apparently Ardour needs it to route from an audio interface to its own tracks. This means the JACK server, really a separate piece of software, has to run at the same time as Mixbus, but a side benefit is that audio can pretty easily be routed into it from other applications.

Why's that important? Well, to me it's important because Ableton handles all of my composition work, and Ableton is not that great at mixing compared with a package like Pro Tools. Unfortunately, ReWire mode in Ableton disables all the VST/AU plugins, rendering a good chunk of my instruments unusable. So I usually end up rendering audio tracks from Ableton and mixing those in PT, which is not necessarily going to get me the best results, aside from being a crappier workflow. I haven't yet gotten Mixbus controlling the transport in Ableton, but it does seem possible.

## UI

Ardour was built originally for Linux. Thankfully, the Mac OS version does not require X11 or a Java VM. It hardly appears "native," though. The reverse-color scheme, the Gnome-style file pickers and very Linux-y UI components are alien, distracting, and not very impressive. Keyboard shortcuts aren't intuitive either: some are borrowed from Pro Tools and that helps, but system-wide commands like Command-backtick for window switching, or even Command-W and Command-H, are nowhere to be found. Many of the commands use Option as their modifier key, which is awkward. Still, a lot of the editing functions are single-key, something that absolutely has to be the case before a DAW can even sit in the same room with Pro Tools. I suppose I could probably re-map them to their PT equivalents, too.

By far the thing you'll notice about the UI the most is the mixer. I've written about [skeuomorphs in audio software](https://medium.com/@mikepropst/grabbin-knobs-764a4c79e503) before, and it's all the same here. Harrison love to tout that they're a console maker, not a software maker, but that works both ways, and their application of a heavy, quasi-realistic mixer design has me gazing longingly at the screenshots of Ardour's relatively clean and straightforward (almost Ableton-esque) mixer. But as they'll tell you, this is a thing meant to replace an analog mixer, and the affordances (in the [Norman sense](http://www.jnd.org/dn.mss/affordances_and.html)) offered by the skeuomorphs help the special features come forward. In a way, it seems like they're intentionally reaching backward, and you can feel it when you mix.

## Fast Access

First off, there's the impressive list of built-in elements on every channel strip, and I admit this is something that I'd probably miss if I were coming from the console world. I'm already enjoying them. In a typical DAW, pretty much everything, with the exception of EQ in some cases, is a plugin.

But in Mixbus, we get a lot:

 * Input gain independent of the fader or the clip gain.
 * a 3-band parametric EQ plus high-pass filter.
 * A compressor with three ratio types, speed control, and makeup gain. The threshold control and gain reduction meter sit right next to the fader and level meter.
 * A number of parameters from the selected insert plugin on the channel.
 * On the 4 mix busses and one master bus, there are tape saturators and different compressors tuned for the purpose.
 * On the master bus, a phase alignment meter and "K-meter" to measure perceived loudness.

What all of this accomplishes is a mix process that involves far less instantiation of plugins, far less opening of separate windows, and a workflow that keeps you looking at the mixer and maintaining a holistic picture of the mix most of the time. This is of course Harrison's goal, and I think they've met it well.

The major downside to this mixer is that there are only 4 "mix busses." You can add any number of busses for reverbs and other effects, but only the mix busses have delay compensation. That means a lot of multiple-bus tricks that analog and PT users employ, such as parallel compression, are out of the picture due to the phasing that'll happen without delay compensation.

## But how does it sound

Again, I admit to knowing little about the console world. I've never wired one, and my understanding of routing and bussing comes largely from years of Pro Tools. Mixbus mirrors the real thing even more closely than PT, which provides both benefits and limitations (as with the limited mix busses). So what does it do for the sound?

I have to say, I've been impressed so far. But I'm not quite sure if it's the much-touted Harrison summing engine or whether the availability of the tools has let me get a good mix faster. Having EQs out front is important because you're tempted to use them. And most tracks are really going to need at least a little, but that tiny thought that pops up when you add a plugin creates enough of a barrier that you might skip it. And when you do add a plugin, it's probably going to have quite a few bands, and a distracting graphical display that makes you think you're doing something right because the curve "looks good" even though you might need more or less on a given band. Mixbus's basic EQ has two shelves and a bandpass that work in limited ranges, a Q that varies based on the amount of boost/cut, and a high-pass. Simple. No controllable Q, no ability to put all 3 bands in the high frequencies and create an insanely hyper-tweaked situation. Of course you can still do all that with the same plugins you know and love now, but you can get a really good mix just by carving each channel as necessary and then applying little touches of the onboard compression.

## Performance

Unfortunately, there are some problems on the performance front. I was able to do some very quick mixes efficiently that sounded great without a lot of hassle, but with tunes that had about 6 tracks and not a lot of plugins (thankfully, you don't need as many plugins with Harrison). But when a client delivered me some songs with 27+ tracks to mix, it died pretty quickly. The meters don't respond, moving knobs and faders ceases to really do anything — the latency all around just gets ridiculous.

## Side by Side?

At the end of the day, Pro Tools still has a lot going for it. I find myself doing a lot of wild and (IMO) creative stuff in PT when it comes to routing and bussing, stuff you just wouldn't be able to do with an analog console — or a DAW that mirrors one too closely.

And though I don't do a *lot* of MIDI work inside PT, I definitely have done some, and it's good to know it's there. I can add a nice synth to a track without going crazy routing multiple programs.

Mixbus also has some good editing tools, some of which are minor UI innovations and others of which are cribbed from PT, but PT is a much faster and more powerful editing machine. It's also one that I know already whereas I've played with Mixbus for about 3 days. I've no doubt I could get pretty handy with the flexible editing functions in Mixbus as well.

At the end of the day, it's a great mixer, competent editor, and it sounds very good with no supplemental software. If you're looking to make great sounding tracks for a lot cheaper than Pro Tools and don't need MIDI functionality beyond sync, it's a really compelling tool.

And it's *fun*.

([Harrison's YouTube channel](http://www.youtube.com/channel/UCtL1SAmjANxmLD_mILAx3Zg) is an easy way to get started playing with real practical functionality within a few minutes. The videos are short and informative, and even have some helpful general mix tips.)
