---
layout: home
title:  Welcome to the ECA GitHub
---

## Course Pages
<ul>
{%- for repo in (site.repos | sort:"name") -%}

{%if repo.site%}
<li>
  <h3>
  <a href="{{site.url}}/courses/{{repo.url}}">
  {{repo.name}}
  </a>
  </h3>
</li>
{%endif%}

{%- endfor -%}

</ul>
