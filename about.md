---
layout: page
title: About
permalink: /about/
---

This is the aggregate website for all Edinburgh College of Art Courses with GitHub Repositories

## Repositories

{% assign repos = site.repos | sort:"name" %}

<ul>
{%- for repo in repos -%}

<li>
  <h4>
  <a href="{{site.base_repo_url}}{{repo.repo}}">
  {{repo.name}}
  </a>
  </h4>
</li>
{%- endfor -%}
</ul>
