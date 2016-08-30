---
---

<!--- ROOT --->
{% for page in site.pages %}{% if page.url == '/' %}
{% assign _path = '/' %}
{% assign _name = 'root' %}
{% assign _depth = '0' %}
{% assign _parent = nil %}
{% assign _parent_depth = nil %}
{% assign _children = '' %}
{% assign _children_depth = '1' %}

<!--- CURRENT --->
<!--- url --->
<!--- name --->
<!--- depth--->
<!--- parent --->
<!--- parent depth --->
<!--- children --->
<!--- children depth --->

<!--- LOOP --->
<!--- url --->
<!--- name --->
<!--- depth--->
<!--- parent --->
<!--- parent depth --->
<!--- children --->
<!--- children depth --->

{% for page in site.pages %}
{% if page.url == '/' %}{{next}}{% else %}
url path = {{page.url}}  
depth = {{ page.url | split: '/' | size }}  
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
