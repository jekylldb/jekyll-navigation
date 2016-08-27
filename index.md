---
---

{% for node in site.pages %}
{{ node.url }}
{% assign directory = node.url | split: "/" %}
{{ directory | size }}
{% endfor %}
