---
layout: home
title:  Welcome to the ECA GitHub
---

### Course Pages

{% assign courses = site.repos | sort:"name" %}

{% for course in courses %}

{% if course.site %}
<li>
  <a href="{{site.url}}/courses/{{course.url}}">
  {{course.name}}
  </a>
</li>
{% endif %}

{%- endfor -%}
