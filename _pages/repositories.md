---
layout: page
permalink: /opensource/
title: Open Source
description: I maintain PySAL/spopt, an open-source Python package for spatial optimisation, and have mentored spopt contributors through Google Summer of Code (2021–2025).
nav: true
nav_order: 7
---

## Featured projects

- [pysal/spopt](https://github.com/pysal/spopt) — spatial optimisation in Python (regionalisation, facility location, transportation-oriented modelling), part of the [PySAL](https://pysal.org/) family; I am one of the maintainers. See the [JOSS paper](https://doi.org/10.21105/joss.03330).
- [qszhao/PTUA2026](https://github.com/qszhao/PTUA2026) — course materials for *Programming Tools for Urban Analytics* at the University of Glasgow (see also the [2025](https://github.com/qszhao/PTUA2025), [2024](https://github.com/qszhao/PTUA2024) and [2023](https://github.com/qszhao/PTUA2023) editions).
- [qszhao/ATUA2026](https://github.com/qszhao/ATUA2026) — course materials for *Advanced Topics for Urban Analytics* at the University of Glasgow.
- [qszhao/Aalto2023-spopt](https://github.com/qszhao/Aalto2023-spopt) — short course on open-source spatial optimisation at Aalto University (2023).
- [qszhao/Research-code-repository](https://github.com/qszhao/Research-code-repository) — code from past and current research projects.

Through **Google Summer of Code** I have mentored spopt contributors every year from 2021 to 2025 — the students and their projects are listed on the [people]({{ '/people/' | relative_url }}) page.

<!-- Live GitHub cards below are served by github-readme-stats/github-profile-trophy;
     they hide themselves automatically when the public instances are rate-limited. -->

{% if site.data.repositories.github_users %}

## GitHub stats

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
{% if site.data.repositories.github_users.size > 1 %}

  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
  </div>

{% endfor %}
{% endif %}
{% endif %}

{% if site.data.repositories.github_repos %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
