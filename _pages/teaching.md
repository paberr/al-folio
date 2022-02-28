---
layout: page
permalink: /teaching/
title: teaching
description: Taught courses.
nav: true
nav_order: 6
---

<!-- pages/teaching.md -->
<!-- Display teaching -->
<div class="teaching">

{%- assign sorted_teaching = site.teaching | group_by_exp: "post", "post.year"  | sort: "year" | reverse -%}
{%- for courses in sorted_teaching -%}
    <h2 class="year">{{courses.name}}</h2>
    <ol class="courses">
    {%- for course in courses.items -%}
    <li>
        <div class="row">
            <div class="col-sm-2 abbr"><abbr class="badge">{{course.type}}</abbr></div>

            <div class="col-sm-8">
                <div class="title">{% if course.details %}<a href="{{ course.url | relative_url }}">{% endif %}{{course.title}}{% if course.semester %} ({{course.semester}}){% endif %}{% if course.details %}</a>{% endif %}</div>
            
                <div class="role">{{course.role}}</div>
            </div>
        </div>
    </li>
    {%- endfor -%}
    </ol>
{% endfor %}

</div>
