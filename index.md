---
---

{% for page in site.pages %}
url = {{page.url}}
{% for section in page.url %}
current = {{ page.url | split: '/' | last }}
depth = {{ section | last | size }}
{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}

{% if forloop.index == 2 %}parent = {{ unit }}{% endif %}

{% endfor %}{% endfor %}{% endfor %}
