	{% for post in category_posts }
	{{ post.date | date:“%Y-%m-%d” }}
	{{ post.title }}
	{ endfor %}
