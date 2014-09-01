---
layout: post
title: "Interesting Point Re: IPv6 Greylisting"
date: 2013-01-15 22:22:00 -0600
comments: false
categories:
- Security
- Networking
- IPv6
- System Administration
---
I was browsing some of the <a href="http://ipv6.he.net/certification/popular_postings.php" target="_blank">IPv6 related blog posts on HE.net</a>, and I came across <a href="http://warrenkwok.blogspot.hk/2013/01/greylisting-and-dual-stack-mail-servers.html" target="_blank">this interesting one</a> regarding greylisting.

<!--more-->

Because of "happy eyes" a connection that immediately fails on IPv6 will fail over to IPv4, so if greylisting is used only on IPv6 it will not be as effective as planned.
