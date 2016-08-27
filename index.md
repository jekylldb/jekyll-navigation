---
---

{% for node in site.pages %}
{{ node.url }}
{% assign parts = node.url | split: "/" %}
{% if node.url != '/' %}
{% assign depth = parts | size | minus:1 %}
{% assign self = node.url | split: "/" | last %}
{% else %}
{% assign depth = parts | size %}
{% assign self = root %}
{% endif %}
{{ depth }}
{{ self }}
{% endfor %}
