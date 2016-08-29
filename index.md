---
---

{% for node in site.pages %}{% for n in node.url %}{% assign categories = n | split: '/' | reverse %}{% for category in categories %}{% if forloop.index == 2 %}{{ category }}<br>{% endif %}{% endfor %}{% endfor %}{% endfor %}
