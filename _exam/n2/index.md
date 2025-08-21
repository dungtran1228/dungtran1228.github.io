---
title: Đề thi N2
layout: default
order: 2
---

Các đề thi và bài luyện tập trình độ N2 - Trung cấp khá

<ul>
{% assign current_dir = page.dir %}
{% for p in site.pages %}
  {% if p.dir == current_dir and p.name != 'index.md' %}
    <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
  {% endif %}
{% endfor %}
</ul>