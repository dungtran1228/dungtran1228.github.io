---
title: N2 đọc hiểu
layout: default
permalink: /n2/speed-master/
---

# Danh sách các bài đọc N2

Speed master N2 dokkai

{% comment %} Tìm tất cả index.md trong thư mục con của _n2 {% endcomment %}
{% assign sub_indexes = site.pages
  | where_exp: "item", "item.path contains '_n2/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != '_n2/index.md'"
  | sort: "order" %}

{% for sub_index in sub_indexes %}
  {% assign path_parts = sub_index.path | split: '/' %}
  {% assign category_folder = path_parts[1] %}
  
  <h2>{{ forloop.index }}. {{ sub_index.title }}</h2>
  {{ sub_index.content | markdownify }}

  <ul>
    {% assign category_pages = site.pages 
       | where_exp: "p", "p.path contains '_n2/'"
       | where_exp: "p", "p.path contains category_folder"
       | where_exp: "p", "p.name != 'index.md'" %}
    {% for p in category_pages %}
      <li><a href="{{ p.url }}">{{ p.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
