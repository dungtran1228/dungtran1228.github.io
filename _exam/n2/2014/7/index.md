---
title: Đề Thi N2 - Năm {{ page.dir | split: '/' | slice: 3 }} - Tháng {{ page.dir | split: '/' | last }}
layout: default
permalink: /exam/n2/{{ page.dir | split: '/' | slice: 3 }}/{{ page.dir | split: '/' | last }}/
---

# Đề Thi N2 - Năm {{ page.dir | split: '/' | slice: 3 }} - Tháng {{ page.dir | split: '/' | last }}

{% assign bai_pages = site.pages
  | where_exp: "item", "item.path contains page.dir"
  | where_exp: "item", "item.name contains 'bai'"
  | where_exp: "item", "item.path != page.path"
  | sort: "name" %}

{% for bai in bai_pages %}
## {{ bai.title | default: bai.name | replace: '.md', '' }}

{{ bai.content | markdownify }}
{% endfor %}