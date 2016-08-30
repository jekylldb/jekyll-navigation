---
---

<!--- ROOT --->
{% for page in site.pages %}
{% if page.url == '/' %}
{% assign _root_path = '/' %}
{% assign _root_page = 'root' %}
{% assign _root_depth = '0' %}
{% assign _root_parent = nil %}
{% assign _root_parent_depth = nil %}
{% assign _root_children = '' %}
{% assign _root_children_depth = '1' %}
{% endif %}
{% endfor %}

<!--- LOOP --->
{% for node in site.pages %}
{% if node.url != '/' %}
{% assign _node_path = node.url %}{% for section in page.url %} 
{% assign _node = node.url | split: '/' | last %}{% assign _node_path_reversed = section | split: '/' | reverse %}{% for _parent in _node_path_reversed %}{% if forloop.index == 2 %}
{% assign _node_parent = _parent %}{% endif %}{% endfor %}
{% assign _node_children = '' %}
{% assign _node_depth = node.url | split: '/' | size | minus:1 %}{% for section in page.url %}
{% assign _node_parent_depth =  node.url | split: '/' | size | minus:2 %}
{% assign _node_children_depth = node.url | split: '/' | size %}
{% endif %}
{% endfor %}

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
