---
title: 'Part 2: Get token'
author: ron
categories:
- instructions
layout: post
date: '2023-05-11T16:04:12-07:00'
permalink: "/part2"
featured: true

---

## Challenge

Welcome back, human! If you're here, it means you were issued your copy of
Get Out Solutions. Congratulations! You're on your way to Space Paradise!

You should have received a username and password via The System. The next
step to getting out is to log into the system and get your special token.
Fire up your "Get Out Solutions" tool, and set it to use the `gettoken`
service.

That token will be required, so you should get it as soon as possible.

> (*bzzzzt* hey, it's me again. I think you've gotta do this. We need to know
> what they're up to. I heard rumours that there's a way to bypass the login
> to get the special test-only token. I'm attaching the service file. Good
> luck! You might be the last hope for Humanity)
>
> (You might want to take a close look at the test token!)

<!--more-->

## Target

`nc -v getout.skullsecurity.org 1337` (or [run it locally if you need/want to](/backup-plan))

## Assets

* [getourpc](/blogdata/getoutrpc) - RPC server
* [getourpc.d](/blogdata/getoutrpc.d) - RPC server (with debug symbols)
* [libgetout.so](/blogdata/libgetout.so) - Shared library
* [libgetout.so.d](/blogdata/libgetout.so.d) - Shared library (with debug symbols)
* [gettoken](/blogdata/gettoken) - RPC service
* [gettoken.d](/blogdata/gettoken.d) - RPC service (with debug symbols)
