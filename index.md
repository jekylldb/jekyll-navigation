---
---

{% for page in site.pages %}

page url = {{page.url}}

{% for section in page.url %}
{% assign current = page.url | split: '/' | last %}
current = {{current}}
{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}
depth = {{forloop.index}}
{% if forloop.index == 2 %}
parent = {{ unit }}
{% endif %}{% endfor %}{% endfor %}{% endfor %}
