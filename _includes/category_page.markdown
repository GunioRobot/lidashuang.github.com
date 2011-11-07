	{% for post in category_posts %}
  <p class="line">
	{{ post.date | date:“%Y-%m-%d” }}
  <a class="title" href="{{ post.url }}">{{ post.title }}</a>
  </p>
	{% endfor %}
