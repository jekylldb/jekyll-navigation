---
---

{% for node in site.pages %}
{% for n in node.url %}

{% assign categories = n | split: '/' | reverse %} <br>
n split reverse size {{ n | split: '/' | reverse | size }} <br>
n split reverse join {{ n | split: '/' | reverse | join: ' ' }} <br>
{% for category in categories %}
{{ category }} <br>
{% endfor %} 
{% endfor %} 
{% endfor %} 
