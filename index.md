---
---

{% for page in site.pages %}
page url = {{page.url}}
depth = {{forloop.index}}
{% for section in page.url %}
{% assign current = page.url | split: '/' | last %}
current = {{current}}
{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}
{% if forloop.index == 2 %}
parent = {{ unit }}
{% endif %}{% endfor %}{% endfor %}{% endfor %}
