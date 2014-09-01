---
layout: post
title: "Debian Package Caching"
date: 2014-07-07 12:53:21 -0500
comments: false
categories: 
- Nerd Projects
- CLI
- IPv6
- Virtualization
- SaltStack
- System Administration
---
By starting to use SaltStack to administrate my Debian VMs I've saved myself a lot of time logging into each machine, running <code>apt-get update; apt-get upgrade</code>. I've used proxies in the past, mostly on satellite links where bandwidth to the Internet was sparse, and needed to be used as efficiently as possible, when possible. I've also run proxies for groups of many systems grabbing the same updates. This time instead of just using squid, or nginx, I checked if there was an apt specific proxy available. There was two "before the fold" options, apt-cache and apt-cacher-ng. I chose NG, as it sounded newer. :-)

<!--more-->

I set up a new VM just for caching updates. This would also give me a Salt Minion to test updates on before rolling the rest of the systems. Another benefit of testing the updates on one system first, is that the entire process is then cached for the rest of the systems.

Installation was simple, <code>apt-get install apt-cacher-ng</code>. Now I just create <code>/etc/apt/apt.conf.d/00proxy</code> like the following on each machine I'd like to pull in the updates. This file can even be pushed via SaltStack. :-)

```text 00proxy
Acquire::http { Proxy "http://199.202.21.16:3142"; };
```

After running apt-cacher-ng for 3 days I've gotten less than 2% cache misses. Over 98% of data has been served via the cache now (almost 7.5GB!).
