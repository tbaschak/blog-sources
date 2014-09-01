---
layout: post
title: "RFC2142: Role Email Accounts"
date: 2014-01-04 00:46:19 -0600
comments: false
categories: 
- Networking
- ISP
- System Administration
---
One of the responsibilities of a ISP is to have various working role email accounts. Both end users, and other network operators expect action on emails sent to accounts like abuse@, support@ or postmaster@. Luckily there is a standard which defines which mailboxes or aliases you should have, <a href="http://tools.ietf.org/html/rfc2142" target="_blank" class="btn btn-mini btn-primary">RFC2142</a>.

Depending on the size of your organization and the number of messages you need to deal with at the various role accounts, it may be helpful to feed those email accounts into a ticketing system to let multiple people handle incoming issues, as well as keeping track of them all to prevent things from slipping between the cracks. These ticketing systems also often automatically send a response back to the sender letting them know that the message has in fact been received (and usually noting the message responder's bot-ness). Two opensource packages which do this quite well, and are used by many ISPS are:

<ul class="nav nav-pills">
	<li><a href="http://otrs.org/" target="_blank">OTRS</a></li>
	<li><a href="http://www.bestpractical.com/rt/" target="_blank">RT</a></li>
</ul>	

<!--more-->

I have used both before in an ISP and/or Enterprise Service Provider environment, OTRS more recently (and with more, and better customizations). Some of the features I really like, and appreciate on a daily basis about OTRS are:

*	GPG signing/encryption support for incoming/outgoing tickets
*	HTML Email support
*	Web-based configuration for 99% of situations
*	Canned answers for FAQs
*	Integrated FAQs (via OTRS developed plugin) with permissions
*	Multiple queues w/ multiple email addresses for each.
*	Inbound &amp; OUTBOUND tickets -- sending out tracked requests via the ticketing system is very handy

I have even <a href="https://github.com/voinetworks/voinet-otrs-theme" target="_blank">forked</a> a very <a href="https://github.com/eea/eionet.otrs.theme" target="_blank">nice looking</a> OTRS theme, and customized it. That is the beauty of GitHub.

OTRS is especially useful in any situation where multiple people need access to one (or more) role email accounts. Email history is logged in the ticket, who sent what to whom. It is useful as an ISP/Enterprise service desk, a personal task tracker, or even a publishing company's job flow tracking system.

