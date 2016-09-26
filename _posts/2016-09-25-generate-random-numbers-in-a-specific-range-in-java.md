---
layout: post
published: true
mathjax: false
featured: false
comments: false
title: Generate Random numbers in a specific range in Java
description: ''
headline: ''
modified: ''
categories: ''
tags: ''
imagefeature: ''
---
Recently I had to generate random numbers in a specific range, and I found that java.util.Random doesn't have a function to do this. However, this functionality is present in ThreadLocalRandom.

###vTip: Use ThreadLocalRandom to generate random numbers in a range

```
import java.util.concurrent.ThreadLocalRandom;
//nextInt(int least,int bound)) is the method signature.
// nextInt is normally exclusive of the top value,
// so add 1 to bound to make it inclusive.
//example to generate values between 5 and 9
ThreadLocalRandom.current().nextInt(5,10); 
```