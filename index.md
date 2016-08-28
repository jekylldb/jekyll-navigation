---
---


{% for node in site.pages %}
{% assign path = node.url | split: '/' | join: ' ' %}
{% assign path_depth = node.url | split: '/' | size | minus:1 %}
{% assign child_depth = node.url | split: '/' | size %}
{% assign parent_depth = node.url | split: '/' | size | minus:2 %}
path = {{path}} <br>
{% endfor %}
