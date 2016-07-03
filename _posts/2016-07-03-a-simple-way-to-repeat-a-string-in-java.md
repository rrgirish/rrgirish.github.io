---
layout: post
published: true
mathjax: false
featured: false
comments: false
title: A simple way to repeat a string in Java
description: ''
headline: ''
modified: ''
categories: ''
tags: ''
imagefeature: ''
---
Recently while working on a task, I had the need to repeat a string a certain number of times in Java. I knew I could write this using a for loop, but I wished to avoid for loops whenever necessary.

**vTiP:**
Thankfully in Java 1.5+, there is a one-liner to do this for you.

```
repeatedStr = new String(new char[n]).replace("\0", str);

```
Where n is the number of times you want to repeat the string and str is the string to repeat.

No imports or libraries needed.