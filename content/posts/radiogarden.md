---
title: "Radio Garden - Vibe Coding"
date: 2025-10-15
draft: false
---

For students in my network: Found this incredible app https://radio.garden/ that streams radio stations from around the world - one click and play! They don't have an official API. Found an unofficial one on Reddit and tried to build a front end - see attached image. All endpoints work except what needs to work - the live stream! 😀 - seems like this is behind Cloudflare. These sorts of apps fascinate me for the cultural possibilities they open up. 

![screenshot](/static/images/1755837859626.jpg)

Unoffical API documentation is here: <https://lnkd.in/gYTCdz35>

Key Endpoints

GET /ara/content/places — List all places with radio stations.

GET /ara/content/page/{placeId} — Get detailed info about a specific place.

GET /ara/content/page/{placeId}/channels — List stations available in a place.

GET /ara/content/channel/{channelId} — Fetch metadata for a specific station.

GET /ara/content/listen/{channelId}/channel.mp3 — Redirect to the live stream URL.

GET /search?q=... — Search across places and stations.

GET /geo — Return client geolocation data.

Build something this weekend folks!
