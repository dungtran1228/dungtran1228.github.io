---
title: Đề thi và luyện tập
layout: default
permalink: /exam/
---

# Danh sách các loại đề thi

Tổng hợp các đề thi và bài luyện tập theo từng cấp độ

{% assign categories = site.pages
  | where_exp: "item", "item.path contains 'exam/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | sort: "order" %}

{% for cat in categories %}
  <h2>{{ forloop.index }}. {{ cat.title }}</h2>
  <p>{{ cat.content | markdownify }}</p>
{% endfor %}