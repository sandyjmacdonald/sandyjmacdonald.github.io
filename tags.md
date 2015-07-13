---
layout: page
title: Tags
permalink: /tags/
---
<!-- site_tags: {{ site_tags }} -->
{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}

<!-- tag_words: {{ tag_words }} -->
{% assign tag_words = site_tags | split:',' | sort %}

<div id="tags">
  <ul class="tag-box inline">
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] | strip_newlines }}{% endcapture %}
    <li><a href="#{{ this_word | cgi_escape }}">{{ this_word }} <span>{{ site.tags[this_word].size }}</span></a></li>
  {% endunless %}{% endfor %}
  </ul>

  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] | strip_newlines }}{% endcapture %}
  <h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>
    <div class="post ml0">
      {% for post in site.tags[this_word] %}{% if post.title != null %}
      <a href="{{ post.url | prepend: site.baseurl }}" class="post-link">
        <h4 class="post-title">{{ post.title }}</h4>
          <p class="post-summary">{{ post.summary }}</p>
       </a>
      {% endif %}{% endfor %}
    </div>
  {% endunless %}{% endfor %}