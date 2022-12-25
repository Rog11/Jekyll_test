---
layout: page
title: newpage
permalink: /newpage/
---

Welcome to my digital garden! My name is LJT, and I am the creator of this space. 

{% for post in site.c[page.category] %}
    <a href="{{ post.url | absolute_url }}">
      {{ post.title }}
    </a>
{% endfor %}
