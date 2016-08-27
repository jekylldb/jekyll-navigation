---
---

{% for node in site.pages %}
{% assign parts = node.url | split: "/" %}
{% if node.url != '/' %}
{% assign item = node.url | split: '/' | join: ', ' %}
{% assign self = node.url | split: "/" | last %}
{% capture parent %}{% for part in parts %}{{ part | remove: self }}{% endfor %}{% endcapture %}
{% if self_depth == 1 %}{% assign parent = 'root' %}{% endif %}
{% assign self_depth = parts | size | minus:1 %}
{% assign child_depth = self_depth | plus:1 %}
{% assign parent_depth = self_depth | minus:1 %}
{% else %}
{% assign self_depth = parts | size %}
{% assign self = 'root' %}
{% assign parent_depth = nil %}
{% assign child_depth = 1 %}
{% endif %}
parts = {{ parts }} <br>
self = {{ self }} <br>
node.url = {{ node.url }} <br>
parent_depth = {{ parent_depth }} <br>
self_depth = {{ self_depth }} <br>
child_depth = {{ child_depth }} <br>
item = {{ item }} <br>
{% endfor %}
