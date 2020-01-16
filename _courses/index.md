---
layout: home
title:  Welcome to the ECA GitHub
---

### Course Pages

{% assign courses = site.repos | sort:"name" %}

{% for course in courses %}

{% if course.site %}
<li>
  <!-- <h4> -->
  <a href="{{site.url}}/courses/{{course.url}}">
  {{course.name}}
  </a>
  <!-- </h4> -->
</li>
{% endif %}

{%- endfor -%}
