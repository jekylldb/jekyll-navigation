---
---

{% for page in site.pages %}
page url = {{page.url}}<br>
{% for section in page.url %}{% assign current = page.url | split: '/' | last %}
current = {{current}}<br>
{% assign categories = section | split: '/' | reverse %}{% for category in categories %}{% if forloop.index == 2 %}parent = {{ category }}<br><br>{% endif %}{% endfor %}{% endfor %}{% endfor %}
