---
---

{% for page in site.pages %}
url path = {{page.url}}
current depth = {{ page.url | split: '/' | size | minus:1 }}
child depth = {{ page.url | split: '/' | size }}
parent depth = {{ page.url | split: '/' | size | minus:2 }}
{% for section in page.url %}
current category = {{ page.url | split: '/' | last }}
{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}
{% if forloop.index == 2 %}
parent category = {{ unit }}
{% endif %}{% endfor %}{% endfor %}{% endfor %}
