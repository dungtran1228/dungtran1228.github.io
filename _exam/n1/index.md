---
title: Đề thi N1
layout: default
permalink: /exam/n1/
---

# Đề thi N1

Các đề thi và bài luyện tập trình độ N1 - Cao cấp

{% assign years = site.pages
  | where_exp: "item", "item.path contains 'exam/n1/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | sort: "year" %}

{% for year_page in years %}
- [{{ year_page.year }}](/exam/n1/{{ year_page.year }}/)
{% endfor %}