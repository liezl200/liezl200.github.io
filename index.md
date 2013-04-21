---
layout: page
title: Index
tagline: Why hello there.
---
{% include JB/setup %}

##Posts:

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

##Notes:
This website is still unfinished. Thanks for checking it out!
