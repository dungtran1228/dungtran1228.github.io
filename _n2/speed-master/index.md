---
title: N2 đọc hiểu
layout: default
permalink: /n2/speed-master/
---

# Danh sách các bài đọc N2

Speed master N2 dokkai

{% assign categories = site.pages
  | where_exp: "item", "item.path contains '_n2/speed-master/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | sort: "order" %}

{% for cat in categories %}
  <h2>{{ forloop.index }}. {{ cat.title }}</h2>
  <p>{{ cat.content | markdownify }}</p>

  <ul>
    {% comment %} Làm sạch cat.dir trước {% endcomment %}
    {% assign cat_dir_clean = cat.dir | remove_first: '/' | remove_last: '/' %}
    
    {% comment %} Lọc pages theo thư mục, sau đó làm sạch path để so sánh {% endcomment %}
    {% assign all_pages = site.pages | where_exp: "p", "p.name != 'index.md'" %}
    {% assign cat_pages = '' | split: '' %}
    
    {% for p in all_pages %}
      {% assign p_path_clean = p.path | remove_first: '/' | remove_last: '/' %}
      {% if p_path_clean contains cat_dir_clean and p.name contains '.md' %}
        {% assign cat_pages = cat_pages | push: p %}
      {% endif %}
    {% endfor %}
    
    {% assign cat_pages = cat_pages | sort: "name" %}
    
    {% for p in cat_pages %}
      <li><a href="{{ p.url }}">{{ p.title | default: p.name | remove: '.md' }}</a></li>
    {% endfor %}
    
    {% if cat_pages.size == 0 %}
      <li><em>Không tìm thấy bài tập nào trong danh mục này.</em></li>
    {% endif %}
  </ul>
{% endfor %}