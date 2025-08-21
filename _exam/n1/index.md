---
title: Đề thi N1
layout: default
order: 1
permalink: /exam/n1/
---

Các đề thi và bài luyện tập trình độ N1 - Cao cấp

<ul>
{% assign current_path = page.path | remove: 'index.md' %}
{% for p in site.pages %}
  {% if p.path contains current_path and p.path != page.path and p.name != 'index.md' %}
    <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
  {% endif %}
{% endfor %}
</ul>