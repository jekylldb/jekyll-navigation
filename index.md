---
layout: default
---


{% assign depth = page.url | split: '/' | size | minus:1 %}
{{ site.pages | group_by:"(depth)" }}
