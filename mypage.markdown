---
layout: page
title: Non-Programming Posts
permalink: /myPage/
---


<ul>
  {% for post in site.categories.non %}
    <li>
      <h2>
        <a href="/Jekyll_test/{{ post.url }}">{{ post.title }}</a>
      </h2>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>

