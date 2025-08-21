---
title: Đề thi tháng 12/2010
layout: default
order: 2
---

Đề thi JLPT tháng 12 năm 2010

<ul>
{% assign current_dir = page.dir %}
{% for p in site.pages %}
  {% if p.dir == current_dir and p.name != 'index.md' %}
    <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
  {% endif %}
{% endfor %}
</ul>