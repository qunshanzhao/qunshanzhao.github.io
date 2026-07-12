---
layout: page
permalink: /people/
title: People
description: Current and past members of the Urban Sensing & Analytics Lab at the University of Glasgow.
nav: true
nav_order: 3
---

<!-- Roster data lives in _data/people.yml; avatars in assets/img/people/.
     To use a real photo for someone, drop it at assets/img/people/<slug>.jpg
     and add `photo: /assets/img/people/<slug>.jpg` to their entry. -->

## Principal Investigator

<div style="display:flex;align-items:flex-start;gap:16px;margin:16px 0 28px;">
  <img src="{{ '/assets/img/prof_pic.jpg' | relative_url }}" alt="Qunshan Zhao" style="width:72px;height:72px;border-radius:50%;object-fit:cover;flex-shrink:0;" loading="lazy">
  <div>
    <strong><a href="{{ '/' | relative_url }}">Qunshan Zhao</a></strong><br>
    Professor of Urban Analytics; Deputy Director, <a href="https://www.ubdc.ac.uk/">Urban Big Data Centre</a>, University of Glasgow.
  </div>
</div>

{% assign anchored_slugs = ',' %}
{% for section in site.data.people.sections %}

## {{ section.title }}

{% for group in section.groups %}
{% if group.title %}

### {{ group.title }}

{% endif %}
<div>
{% for m in group.members %}
{% if m.photo %}{% assign avatar = m.photo %}{% else %}{% assign avatar = '/assets/img/people/' | append: m.slug | append: '.svg' %}{% endif %}
{% assign slug_token = m.slug | prepend: ',' | append: ',' %}
  <div {% unless anchored_slugs contains slug_token %}id="{{ m.slug }}" {% assign anchored_slugs = anchored_slugs | append: m.slug | append: ',' %}{% endunless %}style="display:flex;align-items:flex-start;gap:14px;margin:14px 0;scroll-margin-top:90px;">
    <img src="{{ avatar | relative_url }}" alt="{{ m.name }}" style="width:56px;height:56px;border-radius:50%;object-fit:cover;flex-shrink:0;" loading="lazy">
    <div>
      <strong>{% if m.url %}<a href="{{ m.url }}">{{ m.name }}</a>{% else %}{{ m.name }}{% endif %}</strong> — {{ m.desc }}
      {% if m.note %}<br><small>{{ m.note }}</small>{% endif %}
    </div>
  </div>
{% endfor %}
</div>
{% endfor %}
{% endfor %}

---

**Prospective members:** funded PhD and postdoc opportunities, application routes, and topic ideas are listed on the [opportunities]({{ '/opportunities/' | relative_url }}) page.
