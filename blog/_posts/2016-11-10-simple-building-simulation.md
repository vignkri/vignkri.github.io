---
layout: post
title: Simple Building Simulation Engine
excerpt: "Taking a look at a random old package for Building simulation."
modified: 2016-06-11
category: blog
tags: [energy, data]
---

I have this tendency to surf the pages of Github searching for repositories that have something to do with energy. Usually, I find interesting stuff that are pretty advanced which I slowly go through every day. So, one such excursion yielded this page: https://github.com/cmiller8/SimpleBuilding. This caught my eye because it hasn't really been updated for the last 4 years and at the same time, based on some interesting research which links to this particular page: http://ulg.academia.edu/StephaneBertagnolio. So, I thought it would be interesting to go take a deep dive into this repository, clean it up a bit and see whether it makes sense, hopefully learning a thing or two about building energy simulation and predict the heating and cooling required in multi-zone commercial buildings.

Before I start, I thought this might be an interesting option to study and write code at the same time. So, I've forked it on my personal github profile where it will mirror changes I discuss over here. Let's get started.

# Make this work in Python 3

The first step is to make the code work in Python 3. Since the code is mostly from 4 years ago, it is written for Python 2.X series rather than the newer Python 3. As soon as ran the main file `python SimpleBuildingEngine.py` it through the print statement error. So, the first step was to fix the print statements. So, in interest of preserving support, the print function was imported from the `__future__` package so that the code runs in both versions of python.

# Cleaning up the code

Before I get deeper into the code and see what it does, it has to be readable. As soon as I opened it up, the PyMode linter went up like a Christmas tree pointing out 244 different errors and warnings. So, step two was basically cleaning up the code. Here are some examples of the cleanup done:

- E265 Block comment should start with '# 'A
- E501 Line too long
- E231 missing whitespace after ','
- E261 at least two spaces before inline comment.
- E225 missing whitespace around operators.

Most of the linter errors were for the space after the '#' for the comments. Once most of the commenting issues cleared out, the warnings dropped dramatically. The other code which contains most of the functions for the engine suffered most of the same issues leading to almost 661 warnings. It took forever to clean up the code so that the lines did not overflow. Additionally, the overwhelming amounts of redundant comments filled up the script to its brim.

For the first time ever, I saw a piece of linter saying: `function` is too complex [mccabe] which refers apparently to the mccabe complexity test. It took quite a lot of time to bring some of the apparent pylinter errors and warnings to proper corrected state. Now that it is done, it makes the editing and reading of the code a bit easier.
