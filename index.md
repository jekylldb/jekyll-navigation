---
---


{% for page in site.pages %}

url = {{page.url}}

depth = {{ page.url | split: '/' | size | minus:1 }}

{% for section in page.url %}

current = {{ page.url | split: '/' | last }}

{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}
{% if forloop.index == 2 %}

parent = {{ unit }}

{% endif %}{% endfor %}{% endfor %}{% endfor %}
