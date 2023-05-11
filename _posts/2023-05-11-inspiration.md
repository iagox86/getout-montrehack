---
title: 'Inspiration'
author: ron
categories:
- hints
layout: post
date: '2023-01-10T08:02:16-08:00'
permalink: "/inspiration"
featured: true
---

This will link to detailed documentation and a write-up for the real-world
vulnerabilities that this challenge is based on.

While this won't give away the literal solutions, it's a big step! Only read
this if you want extra information!
<!--more-->

The vulnerabilities that this is based on are originally in Rocket Software's
UniRPC service, and are documented in detail
[in a blog post I wrote](https://www.rapid7.com/blog/post/2023/03/29/multiple-vulnerabilities-in-rocket-software-unirpc-server-fixed/).
I'm also linking my PoCs and Metasploit modules, though those won't work for
the CTF - it's different enough that you need to write your own. :)

The specific vulnerabilities are:

* Part 1 is the software in general: see [libneptune](https://github.com/rbowes-r7/libneptune) for the full protocol
* Part 2 is based on CVE-2023-28503, which is an authentication bypass in `udadmin`; [PoC](https://github.com/rbowes-r7/libneptune/blob/main/udadmin_authbypass_oscommand.rb) / [Metasploit module](https://github.com/rapid7/metasploit-framework/blob/master/modules/exploits/linux/misc/unidata_udadmin_auth_bypass.rb)
* Part 3 is based on CVE-2023-28502, which is a stack buffer overflow in `udadmin`; [PoC](https://github.com/rbowes-r7/libneptune/blob/main/udadmin_stackoverflow_password.rb) / [Metasploit module](https://github.com/rapid7/metasploit-framework/blob/master/modules/exploits/linux/misc/unidata_udadmin_password_stack_overflow.rb)

My NorthSec talk (in 2 days) will talk about this in detail as well, but I
can't share that yet!
