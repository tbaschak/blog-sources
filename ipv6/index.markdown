---
layout: page
title: "IPv6"
comments: false
sharing: true
footer: false
navbar: IPv6
---
Growing up with one single public IP for most of my teen and early adult years, first on dialup, then on ADSL and Cable -- all with NAT -- I knew the value of end to end connectivity. NAT is a pain when you have a single public IP, and you have two similar applications (asterisk + iChat it happened to be) which require the same ports behind NAT. This is where ALG's, etc are supposed to help, but they often end up causing their own problems and need to be disabled.

Once I had connected my first IPv6 over IPv4 tunnel to HE.net, and then setup my first routed /64 network, I was hooked. "All the pain of port forwarding with IPv4 and NAT can go away when this becomes the norm," I thought. Unfortunately, that was over 10 years ago now, and while some parts of the Internet are IPv6 enabled, still too much of it is IPv4 only.

I now maintain a dedicated [Manitoban ASN IPv6 Status page](/ipv6/manitoban-asn-status/) with the status (Active/Inactive/IPv4/IPv6) of all ASNs that operate in Manitoba, or are Manitoban companies.

Below is a list of all blog posts tagged under the IPv6 category in my blog. I write about my IPv6 experiences quite often, to help encourage friends, colleagues, and customers to plan out and make the jump to IPv6 as well.

<ul class="nav nav-pills">
{% for post in site.categories.ipv6 reverse %}
  <li><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a></li>
{% endfor %}
</ul>
