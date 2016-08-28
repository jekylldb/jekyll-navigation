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
{% assign url_array = node.url | split: '/' | join: ' ' %}
{% assign url_array_reverse = url_array | split ' ' | reverse | join: ' ' %}
  {% if node.url == "/" %}
    {% assign depth = url_array | size %}{% else %}{% assign depth = node.url | split: '/' | size | minus:1 %}
  {% endif %}
{% assign child = depth | plus:1 %}
{% assign parent = depth | minus:1 %}
url_array = {{url_array}} <br>
url_array_reverse = {{url_array_reverse}} <br>
depth = {{depth}} <br>
child = {{child}} <br>
parent = {{parent}} <br>
{% endfor %}
