---
layout: post
title: "Enabling IPv6 on Cisco 3560/3750"
date: 2013-01-03 12:39:00 -0600
comments: false
categories:
- Nerd Projects
- IPv6
- ISP
- System Administration
---
There are a few steps required to enable full support for IPv6 on a Cisco Catalyst 3560 or 3750.

<!--more-->

Firstly, you need to change the sdm prefer to
<pre>sdm prefer dual-ipv4-and-ipv6 (default | routing | vlan)</pre>
which will require a reboot. If you need to do IPv4 route-maps for policy-based routing, you will want
<pre>sdm prefer dual-ipv4-and-ipv6 routing</pre>
Next you will need to enable
<pre>ipv6 unicast-routing</pre>
This is much the same as "ip routing" for IPv4 routing. You can also specify no ipv6 source-route the same as IPv4.

The next step is to either set the interface to automatically attempt autoconfiguration by simply using
<pre>ipv6 enable</pre>
or staticly assign an ipv6 address with
<pre>ipv6 address 2604:4280:D00D:200::1/64</pre>
This will turn on advertising as well, and clients will autoconfigure themselves to match the prefix.

Routing protocols work much the same as with IPv4, although you will find that there is less configuration needed in the "router" section, and more in the individual interface.
