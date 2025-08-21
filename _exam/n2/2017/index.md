---
title: tháng 7
layout: default
---

# Danh sách các bài đọc N2

Speed master N2 dokkai

{% assign categories = site.pages
  | where_exp: "item", "item.path contains '_n2/marugoto/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | sort: "order" %}

{% for cat in categories %}
  <h2>{{ forloop.index }}. {{ cat.title }}</h2>
  <p>{{ cat.content | markdownify }}</p>
{% endfor %}