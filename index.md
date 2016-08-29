---
---

{% for node in site.pages %}
{% for n in node.url %}

{% assign categories = n | split: '/' | reverse %} <br>
n split reverse size {{ n | split: '/' | reverse | size }} <br>
n split reverse join {{ n | split: '/' | reverse | join: ' ' }} <br>
n split reverse size {{- n | split: '/' | reverse | size -}} <br>
n split reverse join split size {{- n | split: '/' | reverse | join: ' ' | split: ' ' | size -}} <br>
<br>
{% for category in categories %}
<br>
{{ category }} <br>
{{ forloop.index[2] }} <br>
{% if forloop.index == 2 }} {{ category }} {% endif %}<br>
{% if forloop.index == '2' }} {{ category }} {% endif %}<br>
{% if forloop.index[2] }} {{ category }} {% endif %}<br>
<br>
{% endfor %} 
{% endfor %} 
{% endfor %} 
