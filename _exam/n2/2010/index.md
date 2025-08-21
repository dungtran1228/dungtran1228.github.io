---
title: Đề thi N2 năm 2010
layout: default
year: 2010
permalink: /exam/n2/2010/
---

# Đề thi N2 năm 2010

{% assign months = site.pages
  | where_exp: "item", "item.path contains 'exam/n2/2010/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | sort: "month" %}

{% for month_page in months %}
## {{ forloop.index }}. {{ month_page.title }}

{% assign month_dir = month_page.path | remove: 'index.md' %}
{% assign questions = site.pages
  | where_exp: "item", "item.path contains month_dir"
  | where_exp: "item", "item.name != 'index.md'"
  | sort: "question_number" %}

{% for question in questions %}
- [{{ question.title }}]({{ question.url }})
{% endfor %}

{% endfor %}