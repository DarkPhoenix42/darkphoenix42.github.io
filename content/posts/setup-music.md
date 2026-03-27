+++
title = "My Offline Music Setup"
date = "2026-03-26T17:26:03+05:30"
author = "Praneeth Sarode"
authorTwitter = "PraneethSarode" #do not include @
cover = ""
coverCaption = ""
tags = ["setup", "music"]
keywords = ["offline music setup",
  "FLAC music collection",
  "music library management",
  "music syncing syncthing",
  "best offline music player",
  "android music player comparison",
  "open source music player",
  "music streaming alternatives",
  "local music vs streaming",
  "music workflow setup",
  "digital music organization",
  "audiophile beginner setup",
  "lossless audio setup",
  "music player with WebDAV"]
description = "A documentation of my music stack i.e., how I download music, sync it across devices, and listen to it, including a comparison of various music players and their features."
showFullContent = false
readingTime = true
hideComments = false
toc = false
color = "" #color from the theme settings
+++


## Introduction

I have a penchant for hoarding FLAC files, even though I [don't have good enough hardware](/posts/setup-hardware#earphones)
and the critical listening skills to appreciate the difference. I just feel good, knowing
that I'm listening to the music in its original quality. 

My music setup follows a simple pipeline:

1. Download music in FLAC format
2. Organize and store it locally
3. Sync it across devices
4. Listen using a feature-rich player on each device.

Here’s how each part works.

## Downloading Music

![SpotiFLAC](/img/music/spotiflac.png)

I use [**SpotiFLAC**](https://github.com/afkarxyz/SpotiFLAC) for downloading FLAC 
files. It uses either Qobuz, Tidal or Amazon Music as the source for the FLAC files,
and doesn't require a subscription.

1. It has a beautiful user interface.
2. It supports downloading music using either a Spotify link or searching for songs/albums by name.
3. It also has support for fetching lyrics & high quality album art and embedding them inside the FLAC files, or downloading them as separate .lrc/.jpg files.

It is under active development, and new features are being added regularly.

## Listening to Music - Laptop

![Namida](/img/music/namida.png)

I recently switched over to [**namida**](https://github.com/namidaco/namida) as the music player of my choice.
Though it is [not truly FOSS](https://github.com/namidaco/namida/issues/37#issuecomment-1780341883), it has many amazing features, 
that compensate for it. In fact, it has so many features that I didn't even know I needed some of them, before I used it.
The following is a list of some features that I found others lacked:

1. It supports YouTube search, video playback, and offline downloads, with SponsorBlock integration built in, which saves time. The controls for video playback are also extensive and very similar to the native YouTube UI.
2. It supports the WebDAV protocol, which allows streaming music from a remote file server. This is useful if you expose your music library over WebDAV using a self-hosted setup.
3. It also has strong music recommendation algorithms that suggest tracks based on what you're currently listening to, your listening history, or even specific time periods and moods.
4. It's UI and behaviour are insanely customizable.

A full list of features can be found on their [GitHub page](https://github.com/namidaco/namida?tab=readme-ov-file#-features).

Before namida, I used [**Harmonoid**](https://harmonoid.com) which had very beautiful animations, 
though it lacked many of the features of namida like online service support, song recommendations ..etc.

## Syncing Music to phone

[**Syncthing**](https://syncthing.net/) is an awesome and very easy to use software 
that allows syncing a folder across devices. It is also open-source.
I store all my downloaded music from SpotiFLAC in a single folder. I run syncthing
as a systemd service on my laptop, and use the app on my [phone](/posts/setup-hardware#mobile-phone)
to sync the folder to my phone. This took maybe 5 minutes to setup, and 
works very reliably. I also use it to sync photos and documents to my phone,
and it works just as well.

## Listening to Music - Phone

I use [namida](https://github.com/namidaco/namida) on my phone as well, since it's 
the only app that has all the features I want.

I've tried a lot of other apps as well, and here's a table that summarizes their features:


| App Name                                                         | FOSS  | Modern UI | Online Search | Playlists/m3u | Navigatable Lyrics | Built-in EQ | WebDAV support | Song recommendations |
| :--------------------------------------------------------------- | :---: | :-------: | :-----------: | :-----------: | :----------------: | :---------: | :------------: | :------------------: |
| [**namida**](https://github.com/namidaco/namida)                 |  ⚠️¹  |    ✅     |      ✅       |      ✅       |        ✅          |     ✅      |      ✅        |         ✅           |
| [**Symfonium**](https://symfonium.app/)                          | Paid  |    ✅     |      ❌       |      ✅       |        ✅          |     ✅      |      ✅        |         ✅           |
| [**RiPlay**](https://github.com/fast4x/RiPlay)                   |  ✅   |    ✅     |      ✅       |      ✅       |        ❌          |     ✅      |      ❌        |         ✅           |
| [**OuterTune**](https://github.com/OuterTune/OuterTune)          |  ✅   |    ✅     |      ✅       |      ❌       |        ✅          |     ❌      |      ❌        |         ✅           |
| [**Gramophone**](https://github.com/FoedusProgramme/Gramophone)  |  ✅   |    ✅     |      ❌       |      ✅       |        ✅          |     ❌      |      ❌        |         ❌           |
| [**Poweramp**](https://powerampapp.com/)                         | Paid  |    ✅     |      ❌       |      ✅       |        ✅          |     ✅      |      ❌        |         ❌           |
| [**Harmonoid**](https://harmonoid.com/)                          |  ⚠️¹  |    ✅     |      ❌       |      ❌       |        ❌          |     ❌      |      ✅        |         ❌           |


> **¹ Note on namida and Harmonoid:** While parts of the source code are public, there are some components whose source code is private, and hence they are not truly open-source. 
> Most of their features are free to use though.

Namida is the clear winner for me here, and it is also under active development, with new features being added regularly.
Although, you may prefer others depending on your requirements, for example:

- If you have a very strict Material 3/Material You design language requirement, you might want to check out Symfonium, Gramophone, or Harmonoid. 
- If you want something that is stricly open-source, you could consider RiPlay or OuterTune, which are both excellent players, 
though they lack some features that I wanted, like built-in EQ.

## Conclusion

This setup has worked surprisingly well for me. It gives me full control over my music, works offline, and doesn’t depend on any subscription.
It does take a bit more effort compared to streaming services, but I prefer owning my collection and being able to manage it exactly how I want.
If you’re building something similar, or have better tools to suggest, I’d be interested to hear about it.