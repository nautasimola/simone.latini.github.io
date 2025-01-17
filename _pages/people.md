---
layout: page
permalink: /people/
title: Team
description: Active Researchers (Under Construction)
display_categories: [toshow]
nav: true
nav_order: 3
---

<!-- pages/people.md -->
<div class="people">
{%- if site.enable_people_categories and page.display_categories %}
  <!-- Display categorized people -->
  {%- for category in page.display_categories %}
  <h2 class="category"></h2>
  {%- assign categorized_people = site.people | where: "category", category -%}
  {%- assign sorted_people = categorized_people | sort: "importance" %}
  <!-- Generate cards for each person -->
  <div class="grid">
    {%- for people in sorted_people -%}
      {% include people.html %}
    {%- endfor %}
  </div>
  {% endfor %}

{%- else -%}
<!-- Display people without categories -->
  {%- assign sorted_people = site.people | sort: "importance" -%}
  <!-- Generate cards for each person -->
  <div class="grid">
    {%- for people in sorted_people -%}
      {% include people.html %}
    {%- endfor %}
  </div>
{%- endif -%}
</div>
