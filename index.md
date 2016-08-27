---
---

{% for node in site.pages %}
{% assign parts = node.url | split: "/" %}
{% if node.url != '/' %}
{% assign depth = parts | size | minus:1 %}
{% assign self = node.url | split: "/" | last %}
{% assign child_depth = depth | plus:1 %}
{% assign parent_depth = depth | minus:1 %}
{% else %}
{% assign depth = parts | size %}
{% assign self = 'root' %}
{% endif %}
{{ node.url }}
{{ depth }}
{{ self }}
{% endfor %}
