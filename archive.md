---
layout: page
title: Archive
---
<div class="post ml0">
	{% for post in site.posts %}
	  {% if not post.visible == 0 %}
		<a href="{{ post.url | prepend: site.baseurl }}" class="post-link">
			<h4 class="post-title">{{ post.title }}</h4>
			<p class="post-summary">{{ post.summary }}</p>
		</a>
	{% endfor %}
</div>
