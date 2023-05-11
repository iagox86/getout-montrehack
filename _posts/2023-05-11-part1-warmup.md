---
title: 'Part 1: Warm up'
author: ron
categories:
- instructions
layout: post
date: '2023-01-10T10:03:16-08:00'
permalink: "/part1"
featured: true
---

## Challenge

It's happened! The "Get Out" program has begun! A select number of humans
will be saved from your dying planet and brought to Space Paradise. Humans
wishing to escape must obtain a copy of the software package, "Get Out
Solutions". Packages have been distributed to your world governments.

To test the software, please configure it to connect to the service listed
below, and run the `ping` function.

> (*bzzzt*...*bzzzzzzt*....are you receiving this? There's more to the "Get
> Out" program than meets the eye. None of us are getting "Get Out
> Solutions". But *I* have access to the server-side packages - I think it's
> just an RPC server. Can you help me figure out how to run their `ping` RPC
> service?)

<!--more-->

## Target

`nc -v getout.skullsecurity.org 1337` (or [run it locally if you need/want to](/backup-plan))

## Assets

* [getourpc](/blogdata/getoutrpc) - RPC server
* [getourpc.d](/blogdata/getoutrpc.d) - RPC server (with debug symbols)
* [libgetout.so](/blogdata/libgetout.so) - Shared library
* [libgetout.so.d](/blogdata/libgetout.so.d) - Shared library (with debug symbols)
* [rpcping](/blogdata/rpcping) - RPC service
* [rpcping.d](/blogdata/rpcping.d) - RPC service (with debug symbols)
