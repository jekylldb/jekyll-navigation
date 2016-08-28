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
item = {% for item in array_reversed %}{{ item.first }}{% endfor %}
array inside = {{ array }}
{% endfor %}

array outside = {{ array }}

{% for item in array %}
    {% assign next_i = forloop.index0 | plus: 1 %}
    {% assign prev_i = forloop.index0 | minus: 1 %}
    {{ items[next_i] }}
    {{ items[prev_i] }}
{% endfor %}
