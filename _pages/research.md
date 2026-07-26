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

**As academic Principal Investigator:**

- **[Sensing Gorbals](https://www.gla.ac.uk/research/az/sustainablesolutions/ourprojects/gallant/innovationfundprojects/sensingchangeheatandairqualityinthegorbals/)** (2025–2026) — community sensing of heat and air quality in the Gorbals, Glasgow (GALLANT Innovation Fund)
- **[SpaceEPC](https://business.esa.int/projects/spaceepc)** (2024–2025) — modelling building energy efficiency at scale with satellite Earth observation (ESA Business Applications)
- **[Building Decarbonisation](https://doi.org/10.1038/s42949-026-00348-7)** (2023–2026) — estimating building energy efficiency and carbon footprint for a net-zero carbon target via urban sensing and AI (Royal Society International Exchanges with NSFC, grant IEC\NSFC\223042)
- **[In-Home Sensors Survey](https://www.understandingsociety.ac.uk/participants/projects/sensor/)** (2023–2025) — environmental sensor data collection in Understanding Society households
- **[HotHome](https://www.mirror.co.uk/news/uk-news/uks-overheating-summer-health-crisis-31597681)** (2023) — investigating summer overheating in UK homes with in-home sensors (with the Bureau of Investigative Journalism; coverage in the Mirror)
- **[Glasgow3D](https://zenodo.org/records/15000747)** (2022–2025) — open large-scale 3D building and tree datasets for Glasgow, constructed from airborne LiDAR point clouds

**As Co-Investigator:**

- **[Urban Big Data Centre — research programme](https://www.ubdc.ac.uk/)** (Co-I, 2019–2030) — big data research to improve social, economic and environmental well-being in cities (PI: Prof Nick Bailey; ESRC grant [ES/S007105/1](https://gtr.ukri.org/projects?ref=ES%2FS007105%2F1))
- **[Urban Big Data Centre — ESRC national data service](https://www.ubdc.ac.uk/)** (Co-I, 2019–2026) — data service extension phases 2 to 4, concluded March 2026 (PI: Prof Nick Bailey; ESRC grant [ES/L011921/1](https://gtr.ukri.org/projects?ref=ES%2FL011921%2F1))
- **[IDEAMAPS Data Ecosystem](https://www.ideamapsnetwork.org/project/ideamaps-data-ecosystem)** (Co-PI, 2022–2026) — a participatory data-modelling ecosystem for deprived-area map production in LMIC cities (PI: Prof João Porto de Albuquerque; Bill &amp; Melinda Gates Foundation)
- **[Human Mobility in Greenspace](https://www.ubdc.ac.uk/research-theme/environment-health/understanding-use-of-urban-greenspaces-with-big-data)** (Co-PI, 2023–2025) — understanding human–nature interactions in urban areas using new forms of big data; ESRC Secondary Data Analysis Initiative (PI: Dr Michael Sinclair; grant [ES/W012979/1](https://gtr.ukri.org/projects?ref=ES%2FW012979%2F1))

**As fellowship mentor and PhD studentship supervisor:**

- **[ColdHome](https://www.ubdc.ac.uk/research-theme/city-modelling-sensing/from-smart-data-to-health-impacts-thermal-simulation-of-indoor-environments-in-uk-cold-homes)** (Fellowship Mentor, 2026–2027) — thermal simulation of indoor environments in UK cold homes; SDR UK Fellowship (Fellow: Dr Mingyu Zhu; grant [UKRI4008](https://gtr.ukri.org/projects?ref=UKRI4008))
- **ESRC (SGSSS) PhD studentships** — [Mohd Sarim](https://gtr.ukri.org/projects?ref=studentship-2760612) (lead supervisor; third-sector employability services with the Salvation Army UK, 2022–2026) and [Yunbei Ou](https://gtr.ukri.org/projects?ref=studentship-2760675) (co-supervisor; [housing market impacts of building energy efficiency regulation](https://theses.gla.ac.uk/86042/), 2022–2026)

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
