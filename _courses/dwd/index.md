---
layout: page
title: Dynamic Web Design
course: Dynamic Web Design
repo_url: dynamic-web-design
---

## Help Pages
{% for course in site.courses %}

{% assign dir = course.url | split:"/" %}

{% if dir[2] == 'dwd' and dir[3] != 'index.html' %}
### [{{course.title}}]({{course.url}})
{{course.excerpt}}
{% endif %}

{% endfor %}
