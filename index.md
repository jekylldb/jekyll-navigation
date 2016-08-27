---
---

{% for node in site.pages %}
{% assign parts = node.url | split: "/" %}
{% if node.url != '/' %}
{% assign self = node.url | split: "/" | last %}
{% capture parent %}{% for part in parts %}{{ part | remove: current }}{% endfor %}{% endcapture %}
{% assign self_depth = parts | size | minus:1 %}
{% assign child_depth = self_depth | plus:1 %}
{% assign parent_depth = self_depth | minus:1 %}

{% else %}
{% assign self_depth = parts | size %}
{% assign self = 'root' %}
{% endif %}
{{ node.url }}
{{ self_depth }}
{{ child_depth }}
{{ parent_depth }}
{{ self }}
{{ parent }}
{% endfor %}
