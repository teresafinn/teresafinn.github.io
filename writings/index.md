---
layout: page
title: Articles and Blog Posts
excerpt: "An archive of the articles I've written."
search_omit: true
image:
  feature: articles1.jpg
  credit: Louis Marcoussis [Public domain], via Wikimedia Commons
  creditlink: https://commons.wikimedia.org/wiki/File%3ALouis_Marcoussis_Homme_%C3%A0_la_pipe_1930.jpg
---

<ul class="post-list">
{% for post in site.categories.articles %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt }}</span>{% endif %}</a></article></li>
{% endfor %}
</ul>
