---
layout: page
title: Workshops
permalink: /workshops/
---

These are the workshops that Digital Development run throughout the semester. Get in touch if you would like to know when the next one is running.

***

{% assign workshops = site.workshops | sort:"name" %}

<ul>
{%- for workshop in workshops -%}

<li>
  <h4>
  <a href="{{site.url}}/{{workshop.url}}">
  {{workshop.name}}
  </a>
  </h4>
</li>
{%- endfor -%}
</ul>
