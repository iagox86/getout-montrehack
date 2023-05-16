---
title: Welcome to Get Out!
author: ron
categories:
- instructions
layout: post
date: '2023-05-11T16:04:46-07:00'
permalink: "/welcome"
featured: true

---

Hello Montrehack!

Get Out are a series of three challenges from BSides San Francisco. You're
going to be reverse engineering an RPC server with three different services!
This is heavily based on a real-life project that the author (Ron) worked on.

Note that this is supposed to be difficult! Since we only have 3 hours, I
provided a bunch of hints on the right, feel free to use them (if you want)!

You can access all the challenges, hints, or solutions on the sidebar on the
right.

<!--more-->

## Challenges

Here are the three challenges:

* [Part 1 - Warm up](/part1) - reverse engineer the protocol
* [Part 2 - Get token](/part2) - bypass authentication checks
* [Part 3 - Apply](/part3) - exploit a vulnerability

## Hints + advice

In the original CTF, players had a total of 48 hours. We only have three! So
I provided a bunch of info to help you jump ahead. My recommendations:

* If you want a pure experience, get the challenges without debug symbols and
  don't look at any of the hints on the right
* If you want a bit of a leg-up, grab the versions of the executables with
  debug symbols (files that end in `.d`)
* If you want a bit of help getting started, read the debugging/forking hints
* If you want a better idea of what you're looking for, read the "inspiration"
  section on the right
* If you get stuck, read the hints for the appropriate level
* If you want to jump ahead a bit more, grab the source code for the appropriate
  level
* If you want to jump ahead a lot, grab the protocol documentation and barebones
  implementation

## Target + backup plan

The target server is getout.skullsecurity.org (192.155.82.12) port 1337.
You can test connectivity with Netcat:

```
$ nc -v getout.skullsecurity.org 1337
Ncat: Version 7.93 ( https://nmap.org/ncat )
Ncat: Connected to 192.155.82.12:1337.
```

The important part is that it says "connected" or "connection open" - it'll vary depending on your netcat version (I'm using `ncat`).

If for some reason that server goes down or doesn't work, you can run the
server locally (on Docker) by following the instructions [here](/backup-plan).
