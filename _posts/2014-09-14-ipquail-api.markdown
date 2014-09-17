---
layout: post
title: "IP Quail API"
date: 2014-09-14 03:03:05 -0500
comments: false
description: "While I've been supporting making requests to ipquail.com with useragent curl and responding with only plaintext, I don't have a formal API for the site. Being inspired by the recent Arin on the Road talks on their Whois-RWS and Reg-RWS systems, I sat out to start to write an API for ipquail.com"
categories:
- Anycast
- Nerd Projects
- CLI
- API
- IPv6
- Programming
- System Administration
---
While I've been supporting making requests to ipquail.com with useragent curl and responding with only plaintext, I don't have a formal API for the site. Being inspired by the recent [Arin on the Road](/blog/2014/09/12/arin-on-the-road/) talks on their Whois-RWS and Reg-RWS systems, I set out to start to write an API for ipquail.com. 

I chose to write it using Python/Flask, and deploy it using uWSGI/nginx. Several hours later, I now have [code up on Github](https://github.com/henchman21/ipquail-api), and a functioning beta version online which returns the remote_addr of the client, JSONified.

<!--more-->

This is the output so far:

	curl -i https://dev.henchman21.net/ip/api/v1.0/remote_addr
	HTTP/1.1 200 OK
	Server: nginx/1.6.1
	Date: Sun, 14 Sep 2014 08:07:43 GMT
	Content-Type: application/json
	Content-Length: 50
	Connection: keep-alive

	{
	  "ip": "2604:4280:134:810:8077:52ea:4b4:609e"
	}


## API Documentation (for now)

> GET /ip/api/v1.0/remote_addr

Gets the current IP address. Accessing via [api|api4|api6].ipquail.com will be possible once publicly deployed.

