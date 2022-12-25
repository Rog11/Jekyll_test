---
layout: page
title: Programming Posts
permalink: /c/
---


<ul>
  {% for post in site.categories.programming %}
    <li>
      <h2>
        <a href="/Jekyll_test/{{ post.url }}">{{ post.title }}</a>
      </h2>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>

