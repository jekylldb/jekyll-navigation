---
---

{% for node in site.pages %}

{% assign array = node.url | split: '/' | join: ' ' %}
{% assign array_reversed = node.url | split: '/' | reverse | join: ' ' %}
{% assign array_depth = node.url | split: '/' | size | minus:1 %}
{% assign child_depth = node.url | split: '/' | size %}
{% assign parent_depth = node.url | split: '/' | size | minus:2 %}

array = {{array}} <br>
array_reversed = {{array_reversed}} <br>
array_depth = {{array_depth}} <br>
child_depth = {{child_depth}} <br>
parent_depth = {{parent_depth}} <br>
item = {% for item in array_reversed %}{{ item }}{% endfor %}

{% endfor %}

{% for i in array_reversed %}
  {% if i != 1 %}
    {% continue %}
  {% else %}
    {{ i }}
  {% endif %}
{% endfor %}

{% for i in (1..5) %}
  {% if i == 4 %}
    {% continue %}
  {% else %}
    {{ i }}
  {% endif %}
{% endfor %}
