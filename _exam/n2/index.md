---
title: Danh Sách Đề Thi N2
layout: default
permalink: /exam/n2/
---

# Danh Sách Đề Thi N2

{% assign years = site.pages
  | where_exp: "item", "item.path contains '_exam/n2/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | map: "dir"
  | uniq
  | sort_natural %}

{% for year in years %}
{% assign year_path = year | split: '/' | last %}
- **Năm {{ year_path }}**
  {% assign months = site.pages
    | where_exp: "item", "item.path contains '_exam/n2/'"
    | where_exp: "item", "item.path contains year_path"
    | where_exp: "item", "item.name == 'index.md'"
    | where_exp: "item", "item.path != page.path"
    | map: "dir"
    | uniq
    | sort_natural %}
  {% for month in months %}
  {% assign month_path = month | split: '/' | last %}
  + [Tháng {{ month_path }}](/exam/n2/{{ year_path }}/{{ month_path }}/)
  {% endfor %}
{% endfor %}