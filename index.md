---
---


{% for page in site.pages %}

url = {{page.url}}

depth = {{ page.path | split: '/' | size }}

{% for section in page.url %}

current = {{ page.url | split: '/' | last }}

{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}
{% if forloop.index == 2 %}

parent = {{ unit }}

{% endif %}{% endfor %}{% endfor %}{% endfor %}
