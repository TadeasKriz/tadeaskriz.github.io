---
title: The new Torch!
---

When I thought that **Torch** is almost ready for our internal projects to use, my coworker [**Karel Piwko**][1] came up with a new idea. Basically, right now, **Torch** was working with reflection to store and load entities. The problem with reflection is its performance overhead, causing that **Torch** was ten times slower than using just plain SQL commands and creating the models yourself. But not anymore! I've started working on **annotation processor** that will go through all your entities and generate metadata which will be static and thus significantly faster.

## Changes to the API

That's what is great about this, there **won't** be any! It will behave completely the same, except it will be an order of magnitude faster! I've been able to design the **annotation processor**'s output in way that it can be easily used by **Torch** with the current API.

## Support by IDE's, build tools

Anything that can supply **javac** an annotation processor parameter is supported. Right now I know it does work with **Maven** and **IntelliJ IDEA**.

[1]: https://plus.google.com/u/0/112976143100224772101
