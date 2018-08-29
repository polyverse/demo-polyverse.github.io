---
layout: post
title:  "Polymorphic Linux for Beginners"
date:   2017-12-07
author: "@archisgore"
tags: [beginner, linux, operations, developer, sysadmin, administrator]
categories: beginner
terms: 1
---

## Introduction

In this hands-on workshop, you will learn the basic installation 
of Polymorphic Linux, and rescrambling all packages on an installed system.

## Getting Started

### Let's with a Linux host
On the right you should see one terminal window, running a fully functional Alpine. 

It is running on our [Play-with-Polyverse](https://play.polyverse.io) infrastructure.

Let's run a command to verify it's the right version.
 
  ```.term1
  cat /etc/alpine-release 
  ```

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

