---
title: Building a useful homelab
date: 2023-02-12
posttype: editorial
tags:
  - homelab
  - technology
---
	
A while back I started getting nervous about hosted services. Google starting to limit storage, Amazon killing off their music hosting, all of these were catalysts but a desire for privacy and a kind of old-school internet experience also drove my plans.

After some semi-successful experimentation with Plex on a Raspberry Pi, I started thinking about how the same priciple could be applied to other services, like photo galleries. Turns out that not only are there a ton of self-hosted, open-source options for doing a lot of things you might want to do, most of them have been containerized to run in Docker.

## The components

### A computer
My machine is not that powerful. It's a 4-core Pentium Lenovo Thinkstation with its main drive replaced with an SSD. It previously ran Mint desktop as a basic home computer. But after I got an old Macbook I didn't really need it, so it seemed like a perfect box to repurpose.

### openmediavault
Far and away the most popular operating system for these kinds of boxes is [openmediavault](https://www.openmediavault.org/), a Debian distro with no desktop but a convenient web interface that allows even a relative dumbo like myself to mount drives and share them with services like SMB or FTP. 

### Portainer
As you might imagine, the web UI of OMV makes one want to do everything via your browser. SSH is not super hard, but it's mighty convenient to use Portainer, a great web UI for Docker.

### Jellyfin
After spending what I consider to be too much money to watch my own stuff (PlexPass at $5/month), I went with [Jellyfin](https://jellyfin.org/), an open-source fork of Emby. I tell you what, we've come a long way since the old XBMC running on an overheating computer attached directly to the TV. It has clients for our computers, iOS and Android devices, and Roku, and perhaps because it doesn't need to do transcoding for those devices, the old computer barely even has to work when streaming to two different devices.

### Navidrome
Music was never a strong point of Plex, though it was capable. [Navidrome](https://navidrome.org) implements the Subsonic API, which is pretty well supported in a range of (admittedly varying-quality) third party apps, though it's better than Subsonic itself, which is Java. Is it your personal Spotify? Not quite, but close enough.

### CUPS
Of course, right? We have a laser printer with no built-in network capabilities, and frankly we've had better luck using this old box than a dedicated print server from Monoprice.

### Paperless-ngx
This is a really great [document archive system](https://paperless-ngx.com/) that lets you specify all kinds of great metadata for finding your stuff when you need it (say, tax time or when the insurance company asks for documentation). An iOS app scans directly into it, where the server then OCRs all documents. From there, machine learning tools start trying to automatically apply metadata based on your defined patterns of text.

### Duplicati
It's a GUI backup tool. Easy cheesy, and now all my stuff is backed up in Backblaze B2. 

### Photos
This is a whole other post. What a fun and frustrating journey.

## Resources
It's hard to overstate the usefulness of **/r/selfhosted** as well as the subreddits for all the individual tools. Lots of people of varying levels of expertise willing to help.

If you have any questions on how I did some of this stuff, hit me on twitter/cohost/FB/whatever and I can try to explain it in my just-enough-to-be-dangerous way.