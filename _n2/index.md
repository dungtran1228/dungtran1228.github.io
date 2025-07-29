---
title: N2 đọc hiểu
layout: default
permalink: /n2/
---

# Danh sách các bài đọc N2

Mô tả chung về luyện đọc hiểu N2...

{% assign sub_indexes = site.pages 
  | where_exp: "item", "item.path contains '_n2/' and item.path != '_n2/index.md' and item.path contains '/index.md'" 
  | sort: "order" %}

{% for sub_index in sub_indexes %}
  {% assign category_folder = sub_index.path | split: '/' | slice: 1, 1 | first %}
  {% assign category_path = '_n2/' | append: category_folder | append: '/' %}
  {% assign category_index_path = '_n2/' | append: category_folder | append: '/index.md' %}
  
  <h2>{{ forloop.index }}. {{ sub_index.title }}</h2>
  <p>{{ sub_index.content | markdownify }}</p>

  <ul>
    {% assign lessons = site.pages 
      | where_exp: "page", "page.path contains category_path and page.path != category_index_path" 
      | sort: "path" %}

    {% for page in lessons %}
      <li><a href="{{ page.url }}">{{ page.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}