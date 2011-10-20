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
Reading 
  <script type="text/javascript" src="http://www.douban.com/service/badge/lidashuang/?show=dolist&amp;n=9&amp;columns=9&amp;cat=book" ></script>

  <div id="footer">
	<address>
		<span class="copyright">
			Content &amp; 
			<a href="/">lidashuang</a>
			<br/>
			(<a rel="licence" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Some rights reserved</a>)			
		</span>
		<span class="engine">
			Powered by 
			<a href="http://github.com/mreid/jekyll/" title="A static, minimalist CMS">Jekyll</a>
			<a href="http://www.vim.org">vim</a>
			<a href="http://www.osser.me">git</a>
			<a href="https://github.com">gitub</a>
		</span>
	</address>
  </div>
