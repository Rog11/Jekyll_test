---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<ul>
  {% for category in site.categories %}
    <li>{{ category | first }}</li>
  {% endfor %}
</ul>
