---
layout: home
---

<h1>Category: {{ page.category }}</h1>

<ul>
  {% for post in site.categories[page.category] %}
    <li>
      <h2>{{ post.title }}</h2>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>
