---
layout: post
title: "ASCII Network Diagrams"
date: 2014-06-29 22:04:16 -0500
comments: false
categories: 
- Networking
- Nerd Projects
- System Administration
---
I've often wondered if there is an easy way to generate ASCII network diagrams like those that appear in text RFC documents. This week I discovered [ASCIIFlow](http://asciiflow.com/).

<!--more-->

ASCIIFlow is really simple to use, and lets you draw boxes, lines, and arrows (for network diagrams and flow charts) using your mouse right in the web browser. It also lets you save/open your text diagrams to/from Google Drive.

```
+-----+    +-----+    +-----+
|Edge1|    |Edge2|    |Edge3|
+--+--+    +--+--+    +--+--+
   |          |          |   
   |       +--+--+       |   
   +-------+BGP1 +-------+   
           +--+--+           
              |              
           +--+--+           
           |VMH1 |           
           +-----+           
```
