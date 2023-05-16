---
title: "Debugging [small hint]"
author: ron
categories:
- hints
layout: post
date: '2023-05-11T16:04:27-07:00'
permalink: "/debugging"
featured: true

---

This will show you how to get `getoutrpc` running in a debugger.

As always, this is an intended part of the challenge, and while you're welcome
to read this to jump ahead, do so at your own discretion!
<!--more-->

First, grab all the executables you need from the challenge page; these include:

* Some variation of the `getoutrpc` executable, which includes the debug version (.d) or the [-nofork version](/forking).
* The shared library - `libgetout.so`
* The service executable(s) - `rpcping`, `gettoken`, and/or `apply` (you can run any number of them simultaneously)

Then, create a file called `rpcservices`, which will look like this (fix the
paths to match your paths):

```
# This is a services file
#
# Each line is in the format:
#
# service_name service_executable

ping /ctf/rpcping
gettoken /ctf/gettoken
apply /ctf/apply
```

Then execute it with `LD_LIBRARY_PATH` set to the current directory (so it can
find `libgetout.so`), and two arguments (the port + the services file):

```
$ LD_LIBRARY_PATH=. ./getoutrpc 1337 ./rpcservices 
ping executes /ctf/rpcping
gettoken executes /ctf/gettoken
apply executes /ctf/apply
Listening on port 1337..
```

If you use a non-forking version, you'll have to restart it after each request
(or each crash!):

```
[ron@ronlab blogdata]$ LD_LIBRARY_PATH=. ./getoutrpc-nofork 1337 ./rpcservices 
ping executes ./rpcping
gettoken executes ./gettoken
apply executes ./apply
Listening on port 1337..
Accepted connection 5
Cleaning up zombies...
Forking
Recv failed: Success
```

Note that some levels require other files to be present - use `strace` to figure
those out!
