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

### Let's start with a Linux terminal
On the right you should see one terminal window, running a fully functional Alpine. 

It is running on our [Play-with-Polyverse](https://play.polyverse.io) infrastructure.

Let's run a command to verify it's the right version.
 
  ```.term1
  cat /etc/alpine-release 
  ```

You can play with it a bit if you'd like. Be sure to remember what you
find in the file `/etc/apk/repositories`.

  ```.term1
  cat /etc/apk/repositories 
  ```


### Repoint Repositories

The next step is incredibly simple. You can do it manually, but we
provide a helpful script to take care of it. Let's run the [free
Polymorphic Linux installer](https://polyverse.io/polymorphic-linux-installation-guide/).

  ```.term1
  curl https://repo.polyverse.io/install.sh | sh -s czcw7pjshny8lzzog8bgiizfr
  ```
  
That was surprisingly simple, huh? What did it do really? You can always
open up the install script, or you can view the contents of
`/etc/apk/repositories` to see what's changed:
 
    ```.term1
    cat /etc/apk/repositories 
    ```
 
 There's new repositories in there. These are Polymorphic, and provide
 all the benefits of advanced scrambling without having to do anything new.    
    
### Let's install a Polymorphic Package

So... what happens next? You use Linux as you would, and our repos take care
of the rest. Let's try it. Why don't we install Apache?

    ```.term1
    apk update && apk add apache2 
    ```

### How do we know it worked?

We can query the Alpine Package Manager's policy, of course!

    ```.term1
    apk policy apache2
    ```

### That was easy. Can we rescramble the ENTIRE OS?

We sure can! Sometimes, the commands are complex, but we provide
distribution-specific examples in our documentation.

    ```.term1
    sed -n -i '/repo.polyverse.io/p' /etc/apk/repositories && apk upgrade --update-cache --available
    ```


### That's all there is to it!

Now you're Polymorphic! It's all done. This can work on one machine,
or a thousand. The process and experience is seamless, turnkey and simple.

The terminal is all yours to play with.

There's a lot more coolness to this. Definitely check out our other tutorials.
