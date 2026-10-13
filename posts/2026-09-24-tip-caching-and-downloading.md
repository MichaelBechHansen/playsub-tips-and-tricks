---
layout: post
title: [tip] Caching, downloading and storage
excerpt: How play:Sub keeps music on your device, and how to stay in control of the space it uses.
date: 2026-09-24
tags: tips, 2026.10
author: Michael.
---

play:Sub can keep music on your device in two ways: **cached** and **downloaded**. Both play without a network connection, but they are treated very differently when space runs low.

### Caching: automatic and temporary
When you play music, play:Sub quietly saves the playing track and the next few tracks in the queue on your device. This is the **cache**. It makes playback smooth, skips re-streaming songs you play often, and lets you keep listening through short network drop-outs.

You can also fill the cache on purpose: choose <b>Cache</b> from the context menu of an album, playlist or track.

The cache has a size limit that you decide. When it runs full, play:Sub makes room by removing the music you have gone longest without playing. This is called <b>LRU</b> (Least Recently Used):

1. Think of the cache as a line of tracks. Every time a track is played, it moves to the back of the line.
2. The track at the front of the line is the one you have gone longest without playing.
3. When the cache grows past its limit, tracks are removed from the front of the line until the cache fits again.
4. The track playing now and the next one in the queue are never removed, nor is a track that is still downloading.

The same thing happens if your device runs low on space: play:Sub removes cached tracks, oldest first, until the free space on the device reaches your <b>Min Free Space</b> setting again. If there are no cached tracks left to remove, you will see a <b>Low Disc Space</b> warning.

In short, the cache looks after itself. Music you play often stays; music you have not played in a while makes room for new music.

### Downloading: yours until you remove it
Choose <b>Download</b> from the context menu to keep music on your device for good, for example before a flight or a trip abroad.

Downloaded music is never removed automatically: not when the cache is full, and not when the device runs low on space. It stays until you remove it yourself.

- **Cached** music arrives automatically as you play, counts towards the cache <b>Max Size</b>, and can be removed at any time to make room.
- **Downloaded** music arrives only when you ask for it, does not count towards <b>Max Size</b>, and stays until you remove it.

**Rule of thumb:** use <b>Download</b> for music you *must* have offline. Let the cache take care of everything else.

### Which versions have what
- **2026.9.22 and later** have both caching and downloading, as described here, plus the <b>Storage and Caching</b> settings screen.
- **Versions before 2026.9.22** only have the cache. There, <b>Download to cache</b> puts music in the same cache as everything else, and it can be removed when the cache runs full.

Music saved by an earlier version counts as cache after you update. To keep an album for good, remove it with <b>Remove Download</b>, then choose <b>Download</b>.

### Managing storage
Go to <b>Settings</b> → <b>Storage and Caching</b> → <b>Manage</b>. The screen has three sections:

**Downloads**
- <b>Space used</b>: how much your downloaded music takes up.
- <b>Remove Downloads</b>: removes all downloaded music. Cached music stays. This may stop playback.

**Cache**
- <b>Space used</b>: how much the cache takes up.
- <b>Max Size</b>: the cache size limit. A larger cache keeps more music on hand; a smaller one saves space.
- <b>Min Free Space</b>: how much free space play:Sub leaves on your device by trimming the cache.
- <b>Clear Cache</b>: empties the cache. Downloaded music stays.

**Image Cache**
- Cover art is cached separately, with its own <b>Max Size</b> and <b>Clear Image Cache</b>. It is trimmed the same way: least recently shown first.

**All of the above**
- <b>Clear All Caches and Downloads</b>: removes all cached and downloaded audio and images in one go.

### Bonus
1. To remove a single album, playlist or track, open its context menu and choose <b>Remove Download</b>. This removes its music from the device, whether it was downloaded or cached. If only some tracks are on the device, the menu shows <b>Partially cached</b>, with options to download, cache or remove the rest.
2. Keep an eye on downloads, as they are not included in the <b>Max Size</b> limit. If your device gets full, check <b>Downloads</b> → <b>Space used</b> first.
3. Deleting a server from play:Sub also removes all of its downloaded and cached music from your device.
