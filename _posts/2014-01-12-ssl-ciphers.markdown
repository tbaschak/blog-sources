---
layout: post
title: "SSL Ciphers"
date: 2014-01-12 23:44:23 -0600
comments: false
categories: 
- SSL
- Networking
- System Administration
---
The SSL/TLS Protocol versions, and Ciphers have never really been an item which people configured very tightly. Lately though, there are very valid reasons to ensure that SSL, where applied, has the best methods available to protect confidentiality/integrity. Sites such as [ssllabs.com](https://www.ssllabs.com/ssltest/analyze.html?d=secure.ciscodude.net) can help test your webservers configurations. Weak ciphers give a false sense of security. There are attacks against SSL/TLS.

<!--more-->

The following is the set I use for this site (at the time of publishing):

```
ssl_protocols  SSLv3 TLSv1 TLSv1.1 TLSv1.2;
ssl_ciphers    ECDH+AESGCM:DH+AESGCM:ECDH+AES256:DH+AES256:ECDH+AES128:DH+AES:ECDH+3DES:DH+3DES:RSA+AES:RSA+3DES:!aNULL:!MD5:!DSS;
```

This is also useful (different config value names) in things like dovecot.conf and also apache's SSL vhost configs.
