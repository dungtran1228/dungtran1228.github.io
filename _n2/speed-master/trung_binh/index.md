---
title: Bài đọc trung bình
layout: default
order: 2
---

Bài đọc trung bình có độ dài vừa phải, yêu cầu bạn hiểu mạch nội dung và kết nối các đoạn thông tin.

<ul>
{% assign current_dir = page.dir %}
{% for p in site.pages %}
  {% if p.dir == current_dir and p.name != 'index.md' %}
    <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
  {% endif %}
{% endfor %}
</ul>