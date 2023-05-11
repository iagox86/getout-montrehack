---
title: 'Backup plan: Running the server locally'
author: ron
categories:
- misc
layout: post
date: '2023-01-10T09:02:16-08:00'
permalink: "/backup-plan"
---

This is a guide on how to run the server locally, just in case the online
version doesn't work (or in case you prefer). Since BSides San Francisco ended,
the challenge is open source.

Obviously, you can get the flags from here. Don't do that unless you want to
skip the challenge!

<!--more-->

## Running challenges locally

First, check them out from GitHub; unfortunately, you need to check out the
full BSidesSF CTF repo:

```
$ git clone https://github.com/bsidessf/ctf-2023-release
$ cd ctf-2023-release/getout1-warmup/challenge/
```

Then build the server for `getout1-warmup` (all three challenges use the same
server):

```
$ docker build . -t getout-server
Emulate Docker CLI using podman. Create /etc/containers/nodocker to quiet msg.
STEP 1/36: FROM debian:bullseye-slim
[...]
STEP 34/36: RUN chmod 0444 /ctf/level3-token.txt
--> f6c99ac749e
STEP 35/36: USER 1000
--> 3588afce462
STEP 36/36: CMD ["/ctf/getoutrpc", "1337"]
COMMIT getout-server
--> 532de789aa3
Successfully tagged localhost/getout-server:latest
532de789aa3dabc176f5ca185e751273ca5274eb2d69594c148298fb5317cdfb
```

Then run the server, forwarding port 1337:

```
$ docker run --rm -it -p1337:1337 getout-server
Emulate Docker CLI using podman. Create /etc/containers/nodocker to quiet msg.
ping executes /ctf/rpcping
gettoken executes /ctf/gettoken
apply executes /ctf/apply
Listening on port 1337..
```

You can test it by connecting to `localhost:1337` in another window:

```
$ docker run --rm -it -p1337:1337 getout-server
Emulate Docker CLI using podman. Create /etc/containers/nodocker to quiet msg.
ping executes /ctf/rpcping
gettoken executes /ctf/gettoken
apply executes /ctf/apply
Listening on port 1337..
```
