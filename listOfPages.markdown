---
layout: page
title: listOfPages
permalink: /listOfPages/
category: c
---

{% paginate site.categories['c'] by 10 %}
  {% for post in paginate.posts %}
    <h2><a href="{{ post.url | absolute_url }}">{{ post.title }}</a></h2>
    <p>{{ post.excerpt }}</p>
  {% endfor %}
  {{ paginate | default_pagination }}
{% endpaginate %}
