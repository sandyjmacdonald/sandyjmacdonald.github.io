---
layout: page
title: Archive
---
<div class="post ml0">
	{% for post in site.posts %}
	  {% if post.visible == 1 %}
		<a href="{{ post.url | prepend: site.baseurl }}" class="post-link">
			<h4 class="post-title">{{ post.title }}</h4>
			<p class="post-summary">{{ post.summary }}</p>
		</a>
	  {% endif %}
	{% endfor %}
</div>
