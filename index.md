---
---

{% for node in site.pages %}
{% assign parts = node.url | split: "/" %}
{% if node.url != '/' %}
{% assign self = node.url | split: "/" | last %}
{% capture parent %}{% for part in parts %}{{ part | remove: self }}{% endfor %}{% endcapture %}
{% capture p %}{{ parts[2] }}{% endcapture %}
{% if self_depth == 1 %}{% assign parent = 'root' %}{% endif %}
{% assign self_depth = parts | size | minus:1 %}
{% assign child_depth = self_depth | plus:1 %}
{% assign parent_depth = self_depth | minus:1 %}
{% else %}
{% assign self_depth = parts | size %}
{% assign self = 'root' %}
{% endif %}
parts = {{ parts }} <br>
self = {{ self }} <br>
node.url = {{ node.url }} <br>
parent_depth = {{ parent_depth }} <br>
self_depth = {{ self_depth }} <br>
child_depth = {{ child_depth }} <br>
p = {{ p }} <br>
{% endfor %}

{% assign beatles = "John, Paul, George, Ringo" | split: ", " %}
{% for member in beatles %}
  {{ member }}
{% endfor %}

{% assign my_array = "apples, oranges, peaches, plums" | split: ", " %}

{{ my_array | reverse | join: ", " }}

{% assign product.tags = "sale", "mens", "womens", "awesome" %}
{{ product.tags[2] }}
