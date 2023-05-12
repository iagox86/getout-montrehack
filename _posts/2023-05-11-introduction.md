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

Note that this is supposed to be difficult! I'll post hints and solutions
throughout the evening. You can choose how much help you want!

You can access all the challenges, hints, or solutions on the sidebar on the
right.

<!--more-->

## Challenges

Here are the three challenges:

* [Part 1 - Warm up](/part1) - reverse engineer the protocol
* [Part 2 - Get token](/part2) - bypass authentication checks
* [Part 3 - Apply](/part3) - exploit a vulnerability

## Debug symbols

I've included binaries both with and without debug symbols with each challenge -
choose your own difficulty! Symbols shouldn't affect my exploitation (at
least, my exploits work against binaries both with and without symbols).

Because we only have limited time, I'd strongly suggest using the versions
*with* debug symbols.

## Hints

I've included a bunch of hints in a column on the right. Some of the hints
verge on spoilers, especially for the earlier levels. I try to outline at the
top of the hint just how spoilery it's going to be.

We have 3 hours to do something that I designed to take up to 48 hours, so
you won't be judged at all for using all the hints!

## Target + backup plan

The target server is getout.skullsecurity.org (192.155.82.12) port 1337.
You can test connectivity with Netcat:

```
$ nc -v getout.skullsecurity.org 1337
Ncat: Version 7.93 ( https://nmap.org/ncat )
Ncat: Connected to 192.155.82.12:1337.
```

If for some reason that server goes down or doesn't work, you can run the
server locally (on Docker) by following the instructions [here](/backup-plan).
