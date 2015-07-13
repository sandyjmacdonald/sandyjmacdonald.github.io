---
layout: page
title: Archive
---

## Blog Posts

{% for post in site.posts %}
  * {{ post.date | date: "%b %-d, %Y" }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}