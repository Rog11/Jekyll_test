---
layout: page
title: c
permalink: /newpage/
category: c
---

<!-- {% for post in site.categories[page.category] %}
    <a href="{{ post.url | absolute_url }}">
      {{ post.title }}
    </a>
{% endfor %} -->

<ul>
  {% for category in site.categories %}
    <li>
      <a href="{{ '/category/' | append: category | first | slugify | absolute_url }}">
        {{ category | first }}
      </a>
    </li>
  {% endfor %}
</ul>
