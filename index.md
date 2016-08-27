---
---

{% for node in site.pages %}
{% assign parts = node.url | split: "/" %}
{% if node.url != '/' %}
{% assign self = node.url | split: "/" | last %}
{% capture parent %}{% for part in parts %}{{ part | remove: self }}{% endfor %}{% endcapture %}
{% if self_depth == '1' %}{% assign parent = 'root' %}{% endif %}
{% assign self_depth = parts | size | minus:1 %}
{% assign child_depth = self_depth | plus:1 %}
{% assign parent_depth = self_depth | minus:1 %}
{% else %}
{% assign self_depth = parts | size %}
{% assign self = 'root' %}
{% endif %}
node.url = {{ node.url | newline_to_br }}
self_depth = {{ self_depth | newline_to_br }}
child_depth = {{ child_depth | newline_to_br }}
parent_depth = {{ parent_depth | newline_to_br }}
self = {{ self | newline_to_br }}
parent = {{ parent | newline_to_br }}
{% endfor %}
