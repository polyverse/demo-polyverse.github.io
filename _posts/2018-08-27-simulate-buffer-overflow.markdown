---
layout: post
title:  "A Real Buffer Overflow"
date:   2017-12-07
author: "@archisgore"
tags: [advanced, linux, security, pentesting]
categories: advanced
terms: 3
---

## Introduction

If you're ever in/around the security world, you hear the term "Buffer Overflow" a
lot. You might even have caused some while programming (we all have.) You might
have seen wonderful graphics detailing them.

And yet... they can be these mystic cryptic things that don't REALLY 
affect real people. This tutorial, adapted from [Roy's excellent blog post](https://blog.polyverse.io/an-intentional-buffer-overflow-hmm-5c357238b687),
uses a tool called [ReadHook](https://github.com/PLEXSolutions/readhook), to inject
a real buffer overflow intentionally, so you can really explore the power of
Polymorphic Linux.

## Getting Started

### Let's start with three Linux hosts

To properly simulate the problem, let's have three terminals:
1. The first is our attacker machine in terminal 1, so we can see it the best.
1. The second is our Victim machine on terminal 2
3. The third is this passive sleeper machine that stays out of the way.... sort of. 
 
### Prep the silent observer
Let's prep the silent innocuous observer first. 
Nothing complex. A simple netcat will do... 
 
  ```.term3
  nc -l 5555 
  ```
  
### What the victim doesn't know, will kill it.

Next up, we're going to launch netcat again on the victim machine. Netcat is this
absolute basic network program you can find. It has a FAR FAR smaller exploit surface
area, compared with a large applicaiton.

Except, our netcat is hiding a secret.... there is a program being injected into it
while it starts, called readhook....

```.term2
docker run --rm --name echo -p 8080:8080 alpine:3.7 sh -c 'wget -q -O /tmp/basehook.so https://github.com/plexsolutions/readhook/releases/download/v1.2.2/basehook.so && wget -q -O /tmp/fullhook.so https://github.com/plexsolutions/readhook/releases/download/v1.2.2/fullhook.so && LD_PRELOAD="/tmp/fullhook.so /tmp/basehook.so" nc -l -p 8080 -e /bin/cat'
```

### Mounting the attack

Now let's mount an attack....



### Repoint Repositories

Let's repoint Alpine repositories to Polymorphic drop-in replacement repositories...

  ```.term1
  curl https://repo.polyverse.io/install.sh | sh -s czcw7pjshny8lzzog8bgiizfr
  ```

We used a trial key for this, found at: https://polyverse.io/polymorphic-linux-installation-guide/  

Even though it is a trial key, the Polymorphic Linux is the same production-grade version
that works on real servers.
  
### Reinstall all packages



### That's all there is to it!

