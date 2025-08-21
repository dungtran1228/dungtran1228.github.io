---
title: Đề thi tháng 12/2010
layout: default
order: 2
permalink: /exam/2010/t12/
---

Đề thi JLPT tháng 12 năm 2010

<ul>
{% assign current_path = page.path | remove: 'index.md' %}
{% for p in site.pages %}
  {% if p.path contains current_path and p.path != page.path and p.name != 'index.md' %}
    <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
  {% endif %}
{% endfor %}
</ul>