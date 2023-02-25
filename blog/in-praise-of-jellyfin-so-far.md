---
title: In praise of Jellyfin (so far)
date: 2023-01-10
posttype: editorial
tags:
  - software
  - nerd shit
---

Lately I've been doing more fighting with Plex (slogan: "Pay $5 a month to use your own server") and my Raspberry Pi-based media server than actually watching or listening anything, so I tried a few new things.
- I repurposed a desktop that I hadn't been using since getting a 2015 Macbook that was just a place to randomly try new distros and desktop environments for no reason.
- I put Openmediavault (the OS) on it, and slapped a Dockerized Jellyfin in there.
- I added Tailscale to the equation so I could get there from the other end of the house (don't ask, our house is bad at internet) or from outside the house.

Unfortunately, Tailscale doesn't let Roku type devices get on my tunnel, so maybe I'll use the old Pi for some kind of perma-VPN or reverse proxy or some shit I clearly do not understand.

But I've found Jellyfin to be more bare-bones yet also much more performant, more likely to direct stream than attempt to transcode, and really a breeze to work with. If you've ever wondered about switching from Plex, it might be for you. If you are wondering about Emby, don't — Jellyfin is an open-sourced fork that is more up to date.