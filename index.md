---
---

{% for node in site.pages %}
{% assign url_array = node.url | split: '/' | join: ' ' %}
{% assign url_array_reverse = node.url | split '/' | reverse | join: ' ' %}
{% assign depth = node.url | split: '/' | size | minus:1 %}
{% assign child = node.url | split: '/' | size %}
{% assign parent = node.url | split: '/' | size | minus:2 %}
url_array = {{url_array}} <br>
url_array_reverse = {{url_array_reverse}} <br>
depth = {{depth}} <br>
child = {{child}} <br>
parent = {{parent}} <br>
{% endfor %}
