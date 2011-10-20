---
layout: blog
title: Home
section: Home

feed: atom.xml
keywords: lidashuang, Blog
---

lidashuang's 程序世界
==========================================


[![Feed icon](/css/feed-icon-14x14.png){:title="Atom feed of recent posts" .right}][feed]
A [feed][] of the most recent posts is also available.

[feed]: /atom.xml

最近更新
------------

{% for post in site.posts limit:10 %}
<div class="section list">
  <h1>{{ post.date | date_to_string }}</h1>
  <p class="line">
  <a class="title" href="{{ post.url }}">{{ post.title }}</a>
  <a class="comments" href="{{ post.url }}#disqus_thread">View Comments</a>
  </p>
  <p class="excerpt">{{ post.excerpt }}</p>
</div>
{% endfor %}

<p>
<a href="past.html">Older Posts &rarr;</a>
</p>
