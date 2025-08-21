---
title: Đề thi N2
layout: default
permalink: /exam/n2/
---

# Đề thi N2

Các đề thi và bài luyện tập trình độ N2 - Trung cấp khá

{% assign years = site.pages
  | where_exp: "item", "item.path contains 'exam/n2/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | where_exp: "item", "(item.dir | remove_first: page.dir) contains '/' == false" %}

{% for year_page in years %}
- [{{ year_page.year }}](/exam/n2/{{ year_page.year }}/)
{% endfor %}