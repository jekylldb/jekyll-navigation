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

{{ forloop.length }} <br>
{{ forloop.index }} <br>
{{ forloop.index0 }} <br>
{{ forloop.rindex }} <br>
{{ forloop.rindex0 }} <br>
{{ forloop.first }} <br>
{{ forloop.last }} <br>

{% for n in node.url %}

n size {{ n | size }} <br>
n split reverse join {{ n | split: '/' | reverse | join: ', ' }} <br>
n split join size {{ n | reverse | split: '/' | join: ', ' | size }} <br>
n reverse split size {{ n | reverse | split: '/' | size }} <br>
n reverse split {{ n | reverse | split: '/' }} <br>

{% endfor %} 
{% endfor %} 
