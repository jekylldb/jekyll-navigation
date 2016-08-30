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
{% assign current = page.url | split: '/' | last %}
current = {{current}}
{% assign categories = section | split: '/' | reverse %}
{% for unit in categories %}
{% if forloop.index == 2 %}  
parent category = {{ unit }}
{% endif %}{% endfor %}{% endfor %}{% endif %}{% endfor %}

{% if current == node_parent and subdir_level == node_level %}<a href='{{node.url}}'>{{node.title}}</a>{% endif %}
