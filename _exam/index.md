---
title: Exam
layout: default
permalink: /exam/
---

<h1>Exam</h1>

{% assign categories = site.pages
  | where_exp: "item", "item.path contains '_exam/'"
  | where_exp: "item", "item.name == 'index.md'"
  | where_exp: "item", "item.path != page.path"
  | where_exp: "item", "(item.path | split: '/') | size == 3" %}

<ul>
{% assign categories = categories | sort: 'title' %}
{% for cat in categories %}
  <li><a href="{{ cat.url }}">{{ cat.title | default: cat.name | remove: '.md' }}</a></li>
{% endfor %}
</ul> 