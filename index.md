---
---

{% for page in site.pages %}
{% if page.url == '/' %}
{{next}}
{% else %}
url path = {{page.url}}  
child depth = {{ page.url | split: '/' | size }}  
current depth = {{ page.url | split: '/' | size | minus:1 }}  
parent depth = {{ page.url | split: '/' | size | minus:2 }}
{% for section in page.url %}  
current category = {{ page.url | split: '/' | last }}
{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}
{% if forloop.index == 2 %}  
parent category = {{ unit }}
{% endif %}{% endfor %}{% endfor %}{% endif %}{% endfor %}
