---
layout: page
title: Research
permalink: /research/
description: Current research themes in the Urban Sensing & Analytics Lab — publications for each theme are on the publications page.
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

## Major funded projects

Selected projects I lead as academic Principal Investigator:

- **[Sensing Gorbals](https://www.gla.ac.uk/research/az/sustainablesolutions/ourprojects/gallant/innovationfundprojects/sensingchangeheatandairqualityinthegorbals/)** (2025–2026) — community sensing of heat and air quality in the Gorbals, Glasgow (GALLANT Innovation Fund)
- **[SpaceEPC](https://business.esa.int/projects/spaceepc)** (2024–2025) — modelling building energy efficiency at scale with satellite Earth observation (ESA Business Applications)
- **[In-Home Sensors Survey](https://www.understandingsociety.ac.uk/participants/projects/sensor/)** (2023–2025) — environmental sensor data collection in Understanding Society households
- **[HotHome](https://www.mirror.co.uk/news/uk-news/uks-overheating-summer-health-crisis-31597681)** (2023) — investigating summer overheating in UK homes with in-home sensors (with the Bureau of Investigative Journalism; coverage in the Mirror)
- **[Glasgow3D](https://zenodo.org/records/15000747)** (2022–2025) — open large-scale 3D building and tree datasets for Glasgow, constructed from airborne LiDAR point clouds

## Research talks

A selection of recorded talks and seminars:

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(320px,1fr));gap:22px;margin-top:14px;">
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/Mdm3oCl3rEU?start=2409" title="Understanding Cities by Urban Sensing and Analytics — CPGIS Educational Webinar Series, March 2024" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">Understanding Cities by Urban Sensing and Analytics — CPGIS Educational Webinar Series (2024)</p>
  </div>
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/CEo5vh9BkL4" title="Introduction to Adzuna job market data — UBDC" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">Introduction to Adzuna job market data — UBDC Employment Data User Group webinar (2022)</p>
  </div>
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/iQPXM-57BkM" title="Towards Urban Analytics 2.0" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">Towards Urban Analytics 2.0 — The Alan Turing Institute &amp; University of Leeds (2021)</p>
  </div>
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/N17ehdINW88" title="Brown Bag Seminar Series — Geographic Data Science Lab, University of Liverpool" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">Brown Bag Seminar Series — Geographic Data Science Lab, University of Liverpool (2021)</p>
  </div>
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/rJT6h267IBo" title="MoHeap 2021 — Workshop on Mobility, Health, and Place, University of Zurich" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">MoHeap 2021 — Workshop on Mobility, Health, and Place, University of Zurich</p>
  </div>
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/tKYkbKpNPDY" title="Articulating strategies to address heat resilience — Spatial Analytics + Data Seminar Series, Newcastle University, 2020" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">Articulating strategies to address heat resilience — Spatial Analytics + Data Seminar Series, Newcastle University (2020)</p>
  </div>
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/Kp_XmAXIhWw" title="An exploration of fuel poverty in the private rental housing market — UBDC" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">An exploration of fuel poverty in the private rental housing market — UBDC Interactive Data Dives (2020)</p>
  </div>
  <div>
    <div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:8px;">
      <iframe src="https://www.youtube-nocookie.com/embed/-OWdtLpHko0" title="GISRUK 2020 — Fuel Poverty and Income Deprivation in Bristol, UK" style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" allowfullscreen loading="lazy"></iframe>
    </div>
    <p style="margin:8px 0 0;font-size:0.95em;">GISRUK 2020 — Fuel Poverty and Income Deprivation in Bristol, UK</p>
  </div>
</div>
