	{% for post in category_posts %}
  <p class="line">
  <a class="title" href="{{ post.url }}">{{ post.title }}</a>
 &nbsp&nbsp	{{ post.date | date_to_string }}
  </p>
	{% endfor %}
