---
layout: page
title: "You Have Landed at CiscoDude.net"
comments: false
sharing: false
footer: false
description: "An Internet Technology themed blog. IPv6, BGP, and System Administration are popular topics."
keywords: "ipv6, bgp, cisco, brocade, routing, ospf, system administration, network administration, nagios, network monitoring, internet"
---
<div class="blog-index" itemscope itemtype="http://schema.org/Blog">
	{% assign index = true %}
	{% for post in site.posts limit: 1 %}
	{% assign content = post.content %}
    <article class="post" itemprop="blogPost" itemscope itemtype="http://schema.org/BlogPosting">

		{% unless page.no_header %}
		<header class="page-header">
			{% unless page.meta == false %}
			<p class="meta text-muted text-uppercase"> 
          		{% include post/date.html %}{% if updated %}{{ updated }}{% else %}{{ time }}{% endif %}
			</p>
			{% endunless %}
			{% if index %}
			<h1 class="entry-title" itemprop="name headline"><a href="{{ root_url }}{{ post.url }}" itemprop="url">{% if site.titlecase %}{{ post.title | titlecase }}{% else %}{{ post.title }}{% endif %}</a></h1>
			{% else %}
			<h1 class="entry-title" itemprop="name headline">
				{% if site.titlecase %}{{ page.title | titlecase }}{% else %}{{ page.title }}{% endif %}
				{% if page.subtitle %}
					<small>
						{% if site.titlecase %}{{ page.subtitle | titlecase }}{% else %}{{ page.subtitle }}{% endif %}
					</small>
				{% endif %}
			</h1>
			{% endif %}
		</header>
		{% endunless %}
		{% if index %}
		<div class="entry-content clearfix" itemprop="articleBody description">{{ content | excerpt }}</div>
		{% capture excerpted %}{{ content | has_excerpt }}{% endcapture %}
		{% if excerpted == 'true' %}
			<footer>
				<a class="btn btn-default" rel="full-article" href="{{ root_url }}{{ post.url }}" itemprop="url">{{ site.excerpt_link }}</a>
				<a class="btn btn-default" href="/blog/" itemprop="url">Recent Blogs</a>
				<a class="btn btn-default" href="/blog/archives/" itemprop="url">Blog Archives</a>
			</footer>
		{% endif %}
		{% else %}
		<div class="entry-content clearfix" itemprop="articleBody description">{{ content }}</div>
		{% endif %}
	</article>
	{% endfor %}

<hr>

</div>
