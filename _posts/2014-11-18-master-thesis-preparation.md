---
layout: post
title: "Master Thesis Preparation"
description: "my master thesis in embedded systems preparation"
category: "embedded systems"
tags: ["master thesis", "embedded systems"]
---
{% include JB/setup %}

I arrived in Stockholm to study in Embedded Systems master programme at KTH almost 3 years ago and at last I am about to start working on my master thesis. The project is System on Chip health care device that is not, _I repeat_, not clichéd fitness smart watch gadget, but I wont say anything more for now :P

The System on Chip is from Nordic Semiconductors with ARM Cortex-M0 CPU and embedded "Bluetooth Low Energy" transceiver. There are couple of other sensors part of the entire setup, but I have not had the time to look at them yet.

I lack experience with such projects. I have few Arduino boards and I love to tinker and experiment with them, but this is much more serious. May be because of my inexperience I am so keen and enthusiastic about this project. I am curious, I learn new things and this fuels my enthusiasm even more.

##Alone in the dark

When you lack experience in a field the best thing you could do to change this is to start getting your hands dirty in the simplest and most efficient way possible. 

At first I read all datasheets, documentation and even source code, then I started thinking in advance what IDE can I use, how to debug the code. I assessed few IDEs and I decided on [emIDE](http://www.emide.org/) as it is free and looks noob-friendly... but it is available only on Windows. That is ok. I am very much used to POSIX, but [Cygwin](https://www.cygwin.com/) and [MingW](http://www.mingw.org/) can save me to some extent and I wont spend too much time in the terminal (*is what I hope for, right now*). 

I created a dummy project with the "hello world" of the embedded systems - the blinky example (i.e. turning on/off built-in LED on the board) and tried to compile and link it within the IDE. It took me some time and pulling hair, but the procedure is simple - look what flags/options the Makefile uses and translate this in the IDE's project configuration. The pulling of hair was due to the horrible/unclear error messages gcc outputs and after few hours on the Internet it boiled down to [difference in `-std=c99` and `-std=gnu99`](http://stackoverflow.com/questions/5313536/whats-the-difference-between-gnu99-and-c99-clang) and the fact that `asm` keyword was used in one of the dependencies. 

Next I tried to debug the sample code, which also took me some time until I unveil how the gdb server interacts with JLink and all the settings and boilerplate. MingW has a port on gdb, so I installed it from there and added it in the PATH and everything worked for my surprise.

##Bare minimum

Building and debugging is the minimum I needed to feel confident that I can do something. Now I have it, but I will forget very fast what dependencies I had to install and how exactly I did it. This [snowflake setup](http://martinfowler.com/bliki/SnowflakeServer.html) is very fragile and wont let me replicate my work on a different machine right away. This is my past experience talking with every single prototype project I have done in my life - 6 months later I can not even build it. So for a change this time I will try to document and even create a bundle with all the software I need. This I would consider bare minimum.

Every project is an iteration in the process of learning things. Don't waste these opportunities and soon you will have your own "bare minimum".

