---
layout: page
permalink: /grants/
title: Grants
nav: true
nav_order: 3
---

<!-- role filter -->
<div id="grant-filters" style="display:flex;flex-wrap:wrap;gap:8px;align-items:center;margin:16px 0 4px;">
  <button type="button" data-role="all" class="grant-filter-btn active" style="padding:0.3rem 0.85rem;border:2px solid currentColor;border-radius:1rem;background:none;font-weight:700;cursor:pointer;">All</button>
  <button type="button" data-role="pi" class="grant-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">As PI</button>
  <button type="button" data-role="coi" class="grant-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">As Co-I</button>
  <button type="button" data-role="other" class="grant-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Mentoring &amp; supervision</button>
</div>

<!-- source filter -->
<div id="grant-src-filters" style="display:flex;flex-wrap:wrap;gap:8px;align-items:center;margin:8px 0 4px;">
  <button type="button" data-src="all" class="grant-src-btn active" style="padding:0.3rem 0.85rem;border:2px solid currentColor;border-radius:1rem;background:none;font-weight:700;cursor:pointer;">All sources</button>
  <button type="button" data-src="external" class="grant-src-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">External</button>
  <button type="button" data-src="internal" class="grant-src-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Internal</button>
</div>

{% assign ext_glasgow = site.data.grants | where: "group", "external" | where: "subgroup", "glasgow" %}
{% assign ext_asu = site.data.grants | where: "group", "external" | where: "subgroup", "asu" %}
{% assign int_glasgow = site.data.grants | where: "group", "internal" | where: "subgroup", "glasgow" %}
{% assign int_asu = site.data.grants | where: "group", "internal" | where: "subgroup", "asu" %}

<div class="grant-section" data-src="external">

<h2 style="margin-top:1.6rem;">External funding (University of Glasgow)</h2>
<p style="margin:4px 0 10px;opacity:0.85;">~£850k as PI and ~£9.2m as Co-I / work-package lead</p>
<div>
{% for grant in ext_glasgow %}
  {% include grant_entry.liquid %}
{% endfor %}
</div>

<h2 style="margin-top:2rem;">External funding (Arizona State University)</h2>
<div>
{% for grant in ext_asu %}
  {% include grant_entry.liquid %}
{% endfor %}
</div>

</div>

<div class="grant-section" data-src="internal">

<h2 style="margin-top:2rem;">Internal funding (University of Glasgow)</h2>
<p style="margin:4px 0 10px;opacity:0.85;">~£315k as PI and ~£253k as Co-I</p>
<div>
{% for grant in int_glasgow %}
  {% include grant_entry.liquid %}
{% endfor %}
</div>

<h2 style="margin-top:2rem;">Internal funding (Arizona State University)</h2>
<div>
{% for grant in int_asu %}
  {% include grant_entry.liquid %}
{% endfor %}
</div>

</div>

<script>
  (function () {
    var role = 'all';
    var src = 'all';
    function apply() {
      document.querySelectorAll('.grant-section').forEach(function (sec) {
        sec.style.display = src === 'all' || sec.dataset.src === src ? '' : 'none';
      });
      document.querySelectorAll('.grant').forEach(function (el) {
        el.style.display = role === 'all' || el.dataset.role === role ? '' : 'none';
      });
      document.querySelectorAll('.grant-filter-btn').forEach(function (b) {
        var active = b.dataset.role === role;
        b.classList.toggle('active', active);
        b.style.fontWeight = active ? '700' : '400';
        b.style.borderWidth = active ? '2px' : '1px';
      });
      document.querySelectorAll('.grant-src-btn').forEach(function (b) {
        var active = b.dataset.src === src;
        b.classList.toggle('active', active);
        b.style.fontWeight = active ? '700' : '400';
        b.style.borderWidth = active ? '2px' : '1px';
      });
    }
    document.addEventListener('DOMContentLoaded', function () {
      document.querySelectorAll('.grant-filter-btn').forEach(function (b) {
        b.addEventListener('click', function () { role = b.dataset.role; apply(); });
      });
      document.querySelectorAll('.grant-src-btn').forEach(function (b) {
        b.addEventListener('click', function () { src = b.dataset.src; apply(); });
      });
    });
  })();
</script>
