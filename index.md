---
---

{% for node in site.pages %}
{% for n in node.url %}

n split reverse {{ n | split: '/' | reverse }} <br>
n split reverse size {{ n | split: '/' | reverse | size }} <br>
n split reverse join {{ n | split: '/' | reverse | join: ' ' }} <br>
n split reverse join size {{ n | split: '/' | reverse | join: ' ' | size }} <br>

{% endfor %} 
{% endfor %} 
