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
    Professor in Urban Analytics; Deputy Director, <a href="https://www.ubdc.ac.uk/">Urban Big Data Centre</a>, Division of Urban Studies & Social Policy, University of Glasgow; Visiting Professor, School of Geography, University College Dublin.
  </div>
</div>

<!-- filter + jump navigation -->
<div id="people-filters" style="display:flex;flex-wrap:wrap;gap:8px;align-items:center;margin:6px 0 2px;">
  <button type="button" data-sec="all" class="people-filter-btn active" style="padding:0.3rem 0.85rem;border:2px solid currentColor;border-radius:1rem;background:none;font-weight:700;cursor:pointer;">All</button>
  <button type="button" data-sec="current-members" class="people-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Current members</button>
  <button type="button" data-sec="past-group-members" class="people-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Past members</button>
  <button type="button" data-sec="google-summer-of-code-students" class="people-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">GSoC students</button>
</div>

<p class="people-jump" style="font-size:0.88em;opacity:0.85;margin:4px 0 0;line-height:1.9;">
  Jump to — <strong>Current:</strong>
  <a href="#g-current-members-postdoctoral-research-associates">Postdocs</a> ·
  <a href="#g-current-members-research-assistants">Research Assistants</a> ·
  <a href="#g-current-members-phd-students">PhD Students</a> ·
  <a href="#g-current-members-academic-visitors">Visitors</a>
  &nbsp;<strong>Past:</strong>
  <a href="#g-past-group-members-postdoctoral-research-associates">Postdocs</a> ·
  <a href="#g-past-group-members-data-scientists">Data Scientists</a> ·
  <a href="#g-past-group-members-phd-graduates">PhD Graduates</a> ·
  <a href="#g-past-group-members-msc-students-and-research-assistants">MSc &amp; RAs</a> ·
  <a href="#g-past-group-members-academic-visitors">Visitors</a>
  &nbsp;<a href="#sec-google-summer-of-code-students"><strong>GSoC</strong></a>
</p>

{% assign anchored_slugs = ',' %}
{% for section in site.data.people.sections %}
{% assign sec_slug = section.title | slugify %}
<div class="people-section" data-sec="{{ sec_slug }}">
  <h2 id="sec-{{ sec_slug }}" style="scroll-margin-top:90px;">{{ section.title }}</h2>
  {% for group in section.groups %}
    {% if group.title %}
      <h3 id="g-{{ sec_slug }}-{{ group.title | slugify }}" style="scroll-margin-top:90px;">{{ group.title }}</h3>
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
</div>
{% endfor %}

---

**Prospective members:** funded PhD and postdoc opportunities, application routes, and topic ideas are listed on the [opportunities]({{ '/opportunities/' | relative_url }}) page.

<script>
  (function () {
    function setFilter(sec) {
      document.querySelectorAll('.people-section').forEach(function (el) {
        el.style.display = sec === 'all' || el.dataset.sec === sec ? '' : 'none';
      });
      document.querySelectorAll('.people-filter-btn').forEach(function (b) {
        var active = b.dataset.sec === sec;
        b.classList.toggle('active', active);
        b.style.fontWeight = active ? '700' : '400';
        b.style.borderWidth = active ? '2px' : '1px';
      });
    }
    document.addEventListener('DOMContentLoaded', function () {
      document.querySelectorAll('.people-filter-btn').forEach(function (b) {
        b.addEventListener('click', function () { setFilter(b.dataset.sec); });
      });
      document.querySelectorAll('.people-jump a').forEach(function (a) {
        a.addEventListener('click', function () { setFilter('all'); });
      });
    });

    function jump() {
      var id = decodeURIComponent(location.hash.slice(1));
      if (!id) return;
      var el = document.getElementById(id);
      if (!el) return;
      setFilter('all');
      el.scrollIntoView({ block: 'start' });
      el.style.transition = 'background-color 0.4s';
      el.style.borderRadius = '8px';
      el.style.backgroundColor = 'rgba(180, 30, 120, 0.14)';
      setTimeout(function () { el.style.backgroundColor = 'transparent'; }, 2200);
    }
    document.addEventListener('DOMContentLoaded', jump);
    window.addEventListener('load', function () { setTimeout(jump, 150); });
    window.addEventListener('hashchange', jump);
  })();
</script>
