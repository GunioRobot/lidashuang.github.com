---
layout: blog
title: Home
section: Home

feed: atom.xml
keywords: lidashuang, Blog
---

lidashuang's note code and so on 
==========================================

_Hi My name_ is [lidashuang](/)'s 

More [information](info.html) about this blog and a complete archive of [past](past.html) posts, are 
available via links at the top of the page.

[![Feed icon](/css/feed-icon-14x14.png){:title="Atom feed of recent posts" .right}][feed]
A [feed][] of the most recent posts is also available.

[feed]: /atom.xml

Recent Posts
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
<script type="text/javascript">
//<![CDATA[
(function() {
		var links = document.getElementsByTagName('a');
		var query = '?';
		for(var i = 0; i < links.length; i++) {
			if(links[i].href.indexOf('#disqus_thread') >= 0) {
				query += 'url' + i + '=' + encodeURIComponent(links[i].href) + '&';
			}
		}
		document.write('<script type="text/javascript" src="http://disqus.com/forums/markreid/get_num_replies.js' + query + '"></' + 'script>');
	})();
//]]>
</script>
