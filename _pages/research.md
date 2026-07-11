---
layout: page
title: research
permalink: /research/
description: current research themes in the Urban Sensing & Analytics Lab. Publications for each theme are on the <a href="/publications/">publications</a> page.
nav: true
nav_order: 1
horizontal: false
---

<!-- pages/research.md -->
<div class="projects">
  {% assign sorted_projects = site.projects | sort: "importance" %}
  <!-- Generate cards for each research theme -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
</div>
