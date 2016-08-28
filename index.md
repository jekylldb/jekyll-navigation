---
---

{% for node in site.pages %}
{% assign parts = node.url | split: "/" %}
{% if node.url != "/" %}
{% assign self = node.url | split: '/' | last %}
{% capture parent %}{% for part in parts %}{{ part | remove: self }}{% endfor %}{% endcapture %}
{% assign backurl = node.url | reverse | split: "/" %}
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
backurl = {{ backurl  }} <br>
backurl[2] = {{ backurl[2] }} <br>
self = {{ self }} <br>
node.url = {{ node.url }} <br>
parent_depth = {{ parent_depth }} <br>
self_depth = {{ self_depth }} <br>
child_depth = {{ child_depth }} <br>
{% endfor %}

{% for node in site.pages %}
{% assign item = node.url | split: '/' | join: ' ' %} item = {{item}} <br>
{% assign item_reverse = node.url | split: '/' | reverse | join: ' ' %} item_reverse = {{item_reverse}} <br>
{% assign item_size = item | split: ' ' | size %} item_size = {{item_size}} <br>
{% endfor %}
