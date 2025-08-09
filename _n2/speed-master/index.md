---
title: N2 đọc hiểu
layout: default
permalink: /n2/
---

# Danh sách các bài đọc N2

Speed master N2 dokkai

{% comment %} Tìm tất cả các file index.md trong thư mục con của _n2/ {% endcomment %}
{% assign sub_indexes = site.pages | where_exp: "item", "item.path contains '_n2/'" | where_exp: "item", "item.path contains '/index.md'" | where_exp: "item", "item.path != '_n2/index.md'" | sort: "order" %}

{% for sub_index in sub_indexes %}
  {% comment %} Lấy tên thư mục category từ path {% endcomment %}
  {% assign path_parts = sub_index.path | split: '/' %}
  {% assign category_folder = path_parts[1] %}
  
  <h2>{{ forloop.index }}. {{ sub_index.title }}</h2>
  <p>{{ sub_index.content | markdownify }}</p>

  <ul>
    {% comment %} Tìm tất cả các file trong category này (trừ index.md) {% endcomment %}
    {% for page in site.pages %}
      {% assign page_parts = page.path | split: '/' %}
      {% if page_parts[0] == '_n2' and page_parts[1] == category_folder and page.path != sub_index.path %}
        <li><a href="{{ page.url }}">{{ page.title }}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}