---
---

{% for page in site.pages %}
page url = {{page.url}}
{% for section in page.url %}
{% assign current = page.url | split: '/' | last %}
current = {{current}}
{% assign categories = section | split: '/' | reverse %}
{% for parent in categories %}{% if forloop.index == 2 %}
parent = {{ parent }}
{% endif %}{% endfor %}{% endfor %}{% endfor %}
