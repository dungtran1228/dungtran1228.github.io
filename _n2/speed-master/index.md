---
title: N2 đọc hiểu
layout: default
permalink: /n2/speed-master/
---

# Danh sách các bài đọc N2

Speed master N2 dokkai

{% comment %}
B1: Lấy tất cả index.md của các thư mục con trong _n2/speed-master/
{% endcomment %}
{% assign categories = site.pages
  | where_exp: "item", "item.path contains '_n2/speed-master/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | sort: "order" %}

{% comment %}
B2: Duyệt qua từng category
{% endcomment %}
{% for cat in categories %}
  <h2>{{ forloop.index }}. {{ cat.title }}</h2>
  <p>{{ cat.content | markdownify }}</p>

  <ul>
    {% comment %}
    B3: Lấy các bài viết trong cùng thư mục của category (loại bỏ index.md)
    {% endcomment %}
    {% assign cat_pages = site.pages
      | where_exp: "p", "p.path contains cat.dir"
      | where_exp: "p", "p.name != 'index.md'" %}
    {% for p in cat_pages %}
      <li><a href="{{ p.url }}">{{ p.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
