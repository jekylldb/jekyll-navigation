---
---

{% for node in site.pages %}
{{ node.url }}
{% assign parts = node.url | split: "/" %}
{% if node.url != '/' %}
{% assign depth = parts | size | minus:1 %}
{% else %}
{% assign depth = parts | size %}
{% endif %}
{{ depth }}
{% assign self = node.url | split: "/" | last %}
{{ self }}
{% endfor %}
