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
  <p>{{ cat.dir | markdownify }}</p>

  <ul>
    {% assign cat_pages = site.pages
      | where_exp: "p", "p.name != 'index.md'"
      | where_exp: "p", "p.name contains '.md'"
      | sort: "name" %}
    
    {% for p in cat_pages %}
      <li><a href="{{ p.url }}">{{ p.title }} {{p.path}}</a></li>
    {% endfor %}
  </ul>
{% endfor %}