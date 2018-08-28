---
layout: post
title:  "Polymorphic Linux for Beginners"
date:   2017-12-07
author: "@archisgore"
tags: [beginner, linux, operations, developer, sysadmin, administrator]
categories: beginner
terms: 2
---

## Introduction

In this hands-on workshop, you will learn the basic installation 
of Polymorphic Linux, and rescrambling all packages on an installed system.

## Getting Started

### What is this terminal in the browser?
On the right you should see one terminal window. You may be asked to login first, 
which you can do either with a [Docker ID](https://hub.docker.com/) or a 
[GitHub](https://github.com) account. Those terminals are fully functional 
terminals running Centos. Actually, they're the commandline for Centos containers 
running on our [Play-with-Polyverse](http://play.polyverse.io) infrastructure. 
When you see code blocks that look like this, you can either click on them 
and they will auto populate, or your can copy and paste them.

  ```.term1
  lsb_release
  ```

### Repoint Repositories

  ```.term1
  curl https://repo.polyverse.io/install.sh | sh -s czcw7pjshny8lzzog8bgiizfr
  ```
  
### Reinstall all packages

### That's all there is to it!

