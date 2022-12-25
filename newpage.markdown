---
layout: page
title: posts in c category
permalink: /newpage/
category: c
---

{% for post in site.categories[page.category] %}
    <a href="{{ post.url | absolute_url }}">
      {{ post.title }}
    </a>
{% endfor %}
