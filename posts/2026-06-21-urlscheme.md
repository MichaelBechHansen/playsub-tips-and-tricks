---
layout: post
title: [2026.6] Url scheme automation
excerpt: Control playSub via playsubapp URL commands.
date: 2026-06-21
tags: 2026.6
author: Michael.
---

play:Sub supports automation via the custom app URL scheme:
> playsubapp://COMMAND?parameters
`COMMAND` can be **set**, **server**, **play**, **pause**, **toggleplaying**, **next**, or **prev**.

When a parameter value contains spaces or special characters, URL encode it. For example, use `David%20Bowie` rather than `David Bowie`.

### playsubapp://set
Adjust player settings using URL parameters.

#### Shuffle on/off
> playsubapp://set?shuffle=on<br>playsubapp://set?shuffle=off

#### Repeat off/all/one/1
> playsubapp://set?repeat=off<br>playsubapp://set?repeat=on<br>playsubapp://set?repeat=1<br>playsubapp://set?repeat=one

#### Equalizer
> playsubapp://set?eq=rock<br>playsubapp://set?eq=voice<br>playsubapp://set?eq=off

#### Replay Gain on/off
> playsubapp://set?replaygain=on<br>playsubapp://set?replaygain=off

#### Crossfade on/off
> playsubapp://set?crossfade=on<br>playsubapp://set?crossfade=off

#### Playback speed [0.5 .. 2.0]
> playsubapp://set?rate=1.3

#### Offline mode on/off
> playsubapp://set?offlinemode=on<br>playsubapp://set?offlinemode=off

#### Sleep timer, minutes or end of track (Since version 2022.1)
> playsubapp://set?sleeptimer=endoftrack<br>playsubapp://set?sleeptimer=15<br>playsubapp://set?sleeptimer=off

### playsubapp://server
Switch server.
> playsubapp://server?url=https://abc.subsonic.org:4043&username=USER&password=PASSWD&name=SrvName&selfsigned=1&tokenauth=1&httpbasicusername=USER&httpbasicpassword=PASS

Required parameters are `url`, `username`, and `password`.
Optional parameters are `name`, `selfsigned`, `tokenauth`, `httpbasicusername`, and `httpbasicpassword`.

### playsubapp://play
Start playback from names, filters, paths, or ids. Multiple play parameters can be combined into one queue.

#### Artists by name
> playsubapp://play?artist=David%20Bowie<br>playsubapp://play?artist=Pink%20Floyd&artist=Roger%20Waters<br>playsubapp://play?artist=Pink*

#### More Like current artist
> playsubapp://play?morelikethis=artist<br>playsubapp://play?morelikethis=topsongs

#### Albums by name
> playsubapp://play?album=Back In Black&album=The Wall<br>playsubapp://play?album=The Wall Disc 1&album=The Wall Disc 2<br>playsubapp://play?album=The Wall Disc*<br>playsubapp://play?album=Ziggy*&album=1. Outside

#### Playlists by name
> playsubapp://play?playlist=Led%20Zepp*

#### Podcasts, unplayed episodes by podcast name
> playsubapp://play?podcast=P6%20Beat%20Elsker*

#### Radio stations by name
> playsubapp://play?radio=DR%20P6*&radio=Radio%20Kaos*<br>playsubapp://play?radio=*

#### Genres
> playsubapp://play?genre=Progressive*

#### Folders by path
> playsubapp://play?folder=ABC<br>playsubapp://play?folder=ABBA/Arrival

#### Items by id
> playsubapp://play?folderId=61730<br>playsubapp://play?artistId=2059<br>playsubapp://play?albumId=6935<br>playsubapp://play?trackId=57897<br>playsubapp://play?playlistId=42
`folderId`, `albumId`, `artistId`, `trackId`, and `playlistId` use server ids.

#### Newest, optional count
> playsubapp://play?newest=albums<br>playsubapp://play?newest=albums,10<br>playsubapp://play?newest=podcasts

#### Favourites, optional count
> playsubapp://play?favourite=albums,3<br>playsubapp://play?favourite=artists<br>playsubapp://play?favourite=songs<br>playsubapp://play?favourite=radios<br>playsubapp://play?favourite=playlists

#### Random, optional count
> playsubapp://play?random=albums,3<br>playsubapp://play?random=artists<br>playsubapp://play?random=songs,42<br>playsubapp://play?random=radios<br>playsubapp://play?random=playlists

#### Years/decades, year range, open ended
> playsubapp://play?years=1968-1972<br>playsubapp://play?years=-1972<br>playsubapp://play?years=2010-

#### Cached items, optional count
> playsubapp://play?cached=albums,3<br>playsubapp://play?cached=artists<br>playsubapp://play?cached=songs,42<br>playsubapp://play?cached=playlists

#### Play with settings
Player settings can be included with a play command.
> playsubapp://play?album=My Audiobook&shuffle=off&repeat=off&crossfade=off&rate=1.5&eq=voice

### Transport controls

#### Resume playing current queue
> playsubapp://play

#### Pause playback
> playsubapp://pause

#### Toggle playback
> playsubapp://toggleplaying

#### Skip
> playsubapp://next<br>playsubapp://prev

### Combining multiple settings

#### Setting everything up for playing some rock:
> playsubapp://set?shuffle=on&repeat=on&replaygain=on&crossfade=on&rate=1&eq=rock

#### Setup audiobook mode:
> playsubapp://play?album=My%20Audiobook&shuffle=off&repeat=off&crossfade=off&rate=1.5&eq=voice
