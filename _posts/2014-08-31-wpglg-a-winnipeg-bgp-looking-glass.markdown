---
layout: post
title: "WpgLG: A Winnipeg BGP Looking Glass"
date: 2014-08-31 21:34:15 -0500
comments: false
categories: 
- Nerd Projects
- IPv6
- System Administration
- Networking
- BGP
- ISP
- CLI
- Programming
---
I've forked [GIXLG](https://github.com/dpiekacz/GIXLG) on github, and I intend to spend my spare time hacking at it. Eventually, once I get my own ASN, I will peer with both local Internet Exchanges, and gather Winnipeg based BGP stats.

<!--more-->

GIXLG is an excellent starting point for what I would like to accomplish. The backend is written in python, and uses [exabgp](https://github.com/Exa-Networks/exabgp) for external BGP communication. It logs updates from various connections to a MySQL database. 

Things I intend to do with GIXLG:

*	improve installation documentation
*	hack on collector.py to log updates to a separate updates table for archiving
	*	I am not 100% if mysql is the proper DB to have a running log of updates in, I am tempted by CouchDB

Eventually I plan on running this as WpgLG, which will be a Winnipeg BGP Looking Glass.
