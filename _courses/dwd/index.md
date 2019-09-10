---
layout: page
title: Dynamic Web Design
course: Dynamic Web Design
repo_url: dynamic-web-design
---

{% for course in site.courses %}

{% assign dir = course.url | split:"/" %}
{{course.title}}
{% if dir[2] == 'dwd' %}

{% endif %}

{% endfor %}
