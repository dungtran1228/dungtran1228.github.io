---
title: Đề thi N1
layout: default
order: 1
---

Các đề thi và bài luyện tập trình độ N1 - Cao cấp

<ul>
{% assign current_dir = page.dir %}
{% for p in site.pages %}
  {% if p.dir == current_dir and p.name != 'index.md' %}
    <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
  {% endif %}
{% endfor %}
</ul>