---
layout: blog
title: 函数式编程
section: Home

feed: atom.xml
keywords: lidashuang, Blog
---

山东理工大学linux小组 http://sdutlinux.org
==========================================


Recent Posts
------------

{% for post in site.categories.fp limit:10 %}
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
