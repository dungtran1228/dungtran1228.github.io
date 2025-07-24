---
title: N2 đọc hiểu
layout: default
permalink: /n2/
---

# Danh sách các bài học N2

<ul>
  {% for page in site.pages %}
    {% if page.path contains '_n2/' and page.path != '_n2/index.md' %}
      <li>
        <a href="{{ page.url }}">{{ page.title }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>