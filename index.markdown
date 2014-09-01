---
layout: page
title: "You Have Landed at CiscoDude.net"
comments: false
sharing: false
footer: false
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

<p>
	Some things here:
	<span class="categories">
		<a class='category label label-primary' href="/blog/" itemprop="url">Latest Blogs</a>
		<a class='category label label-primary' href="/blog/archives/" itemprop="url">Blog Archives</a>
		<a class='category label label-primary' href="/ipv6/" itemprop="url">IPv6</a>
		<a class='category label label-primary' href="/ipv6/manitoban-asn-status/" itemprop="url">Manitoban ASN IPv6 Status</a>
		<a class='category label label-primary' href="/about/" itemprop="url">About</a>
		<a class='category label label-primary' href="/presentations/" itemprop="url">Presentations</a>
		<a class='category label label-primary' href="/blogroll/" itemprop="url">Blog Roll</a>
		<a class='category label label-primary' href="/contact/" itemprop="url">Contact</a>
		<a class='category label label-primary' href="/atom.xml" itemprop="url">Feed (atom.xml)</a>
	</span>
</p>

<p>
	Related things, which are not here:
	<span class="categories">
		<a class='category label label-primary' href="https://theodorebaschak.com" itemprop="url">TheodoreBaschak.com</a>
		<a class='category label label-primary' href="http://ipquail.com" itemprop="url">IP Quail</a>
		<a class='category label label-primary' href="http://hextet.ca" itemprop="url">Hextet Systems</a>
		<a class='category label label-primary' href="https://henchman21.net" itemprop="url">Henchman 21</a>
		<a class='category label label-primary' href="https://github.com/tbaschak" itemprop="url">github.com/tbaschak</a>
		<a class='category label label-primary' href="http://tbaschak.github.io" itemprop="url">tbaschak.github.io</a>
	</span>
</p>

<hr>

<b>Thank you for visiting CiscoDude Networks.</b>

</div>
