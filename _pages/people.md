---
layout: page
title: People
permalink: /people/
description: Lab Members
nav: true
nav_order: 4
display_categories: [Current Members, Research Fellows, PhD Students, Research Analysts & Technicians, Affiliated Members, Alumni]
horizontal: false
---
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_people = site.people | where: "category", category -%}
  {%- assign sorted_people = categorized_people | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="grid">
    {%- for project in sorted_people -%}
      {% include people.html %}
    {%- endfor %}
  </div>
  {% endfor %}

{%- else -%}
  <!-- pages/people.md -->
  <div class="projects">
  <!-- Display projects without categories -->
    {%- assign sorted_people = site.people | sort: "importance" -%}
    <!-- Generate cards for each project -->
    <div class="grid">
      {%- for project in sorted_people -%}
        {% include people.html %}
      {%- endfor %}
    </div>
{%- endif -%}
</div>