---
layout: post
title: [2019.2] Url scheme automation
excerpt: Control playSub via playsubapp URL commands
date: 2019-08-03
tags: 2019.2
author: Michael.
---

play:Sub supports automation via the custom app URL-scheme: playsubapp://
> playsubapp://COMMAND?parameters
Where COMMAND is one of: **set**, **server**, **play** and **pause**

### playsubapp://set 
Adjust various settings, using url parameters 
#### Shuffle on/off
> playsubapp://set?shuffle=on<br>playsubapp://set?repeat=off


#### Equalizer
> playsubapp://set?eq=rock<br>playsubapp://set?eq=on<br>playsubapp://set?eq=off

#### Replay Gain on/off
> playsubapp://set?replaygain=on<br>playsubapp://set?replaygain=off

#### Crossfade on/off
> playsubapp://set?crossfade=on<br>playsubapp://set?crossfade=off

#### Playback speed [0.5 .. 2.0]
> playsubapp://set?rate=1.3

#### Controlling offline mode
> playsubapp://set?offlinemode=on<br>playsubapp://set?offlinemode=off


### playsubapp://server
Switching server
> playsubapp://server?url=https://abc.subsonic.org:4043&username=USER&password=PASSWD&n=SrvName&selfsigned=1&tokenauth=1&httpbasicusername=USER&httpbasicpassword=PASS

### playsubapp://play
Playing specific things

#### Play specific artist
> playsubapp://play?artist=david bowie<br>playsubapp://play?artist=the Beatles

#### Play multiple artists
> playsubapp://play?artists=pink floyd&artist=roger waters<br>playsubapp://play?artists=pink*

#### Play albums
> playsubapp://play?album=back in black&album=the wall<br>playsubapp://play?album=the wall disc 1&album=the wall disc 2<br>playsubapp://play?album=the wall disc *<br>playsubapp://play?album=ziggy*&album=1. outside

#### Playlists
> playsubapp://play?playlist=led zepp*

#### Podcasts, unplayed episodes
> playsubapp://play?podcast=p6 beat elsker*

#### Radio stations
> playsubapp://play?radio=dr p6*&radio=radio kaos*<br>playsubapp://play?radio=*

#### Genres
> playsubapp://play?genre=progressive*

#### Folders by path (exact match)
> playsubapp://play?folder=abc<br>playsubapp://play?folder=abba/arrival

#### Folders by Subsonic-ID
> playsubapp://play?folderid=61730<br>playsubapp://play?folderid=60894

#### Newest (optional count)
> playsubapp://play?newest=albums<br>playsubapp://play?newest=albums,10<br>playsubapp://play?newest=podcasts

#### Favourites (optional count)
> playsubapp://play?favourite=albums,3<br>playsubapp://play?favourite=artists<br>playsubapp://play?favourite=songs<br>playsubapp://play?favourite=radios<br>playsubapp://play?favourite=playlists

#### Random (optional count)
> playsubapp://play?random=albums,3<br>playsubapp://play?random=artists<br>playsubapp://play?random=songs,42<br>playsubapp://play?random=radios<br>playsubapp://play?random=playlists

#### Years/decades (year range, open ended)
> playsubapp://play?years=1968-1972<br>playsubapp://play?years=-1972<br>playsubapp://play?years=2010-

#### Cached items
> playsubapp://play?cached=albums,3<br>playsubapp://play?cached=artists<br>playsubapp://play?cached=songs,42<br>playsubapp://play?cached=playlists


### Resume playing current queue
> playsubapp://play

### Pausing playback
> playsubapp://pause

### Combining multiple commands:

#### Setting everything up for playing some rock:
> playsubapp://set?shuffle=on&repeat=on&replaygain=on&crossfade=on&rate=1&eq=rock

#### Setup audiobook mode:
> playsubapp://set?shuffle=off&repeat=off&crossfade=off&rate=1.5&eq=voice&play=an-audiobook
