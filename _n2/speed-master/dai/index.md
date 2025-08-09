---
title: Bài đọc dài
layout: default
order: 3
---

Các bài đọc dài mô phỏng đoạn văn trong đề thi thực tế, giúp bạn luyện kỹ năng đọc hiểu chuyên sâu và quản lý thời gian làm bài.

<ul>
{% assign current_dir = page.dir %}
{% for p in site.pages %}
  {% if p.dir == current_dir and p.name != 'index.md' %}
    <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
  {% endif %}
{% endfor %}
</ul>