---
layout: page
permalink: /grants/
title: Grants
nav: true
nav_order: 3
---

External funding: **~£823k as PI** and **~£8.8m as Co-I / work-package lead**; internal (University of Glasgow) funding: **~£315k as PI** and **~£243k as Co-I** — full economic cost (FEC) totals as listed in my [CV]({{ '/assets/pdf/Qunshan_Zhao_CV.pdf' | relative_url }}).

<!-- role filter -->
<div id="grant-filters" style="display:flex;flex-wrap:wrap;gap:8px;align-items:center;margin:16px 0 4px;">
  <button type="button" data-role="all" class="grant-filter-btn active" style="padding:0.3rem 0.85rem;border:2px solid currentColor;border-radius:1rem;background:none;font-weight:700;cursor:pointer;">All</button>
  <button type="button" data-role="pi" class="grant-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">As PI</button>
  <button type="button" data-role="coi" class="grant-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">As Co-I</button>
  <button type="button" data-role="other" class="grant-filter-btn" style="padding:0.3rem 0.85rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Mentoring &amp; supervision</button>
</div>

{% assign ext_review = site.data.grants | where: "group", "external" | where: "status", "review" %}
{% assign ext_funded = site.data.grants | where: "group", "external" | where: "status", "funded" %}
{% assign int_funded = site.data.grants | where: "group", "internal" | where: "status", "funded" %}

<h2 style="margin-top:1.6rem;">External funding</h2>

<h3 style="margin-top:1rem;opacity:0.85;">Under review</h3>
<div>
{% for grant in ext_review %}
  {% include grant_entry.liquid %}
{% endfor %}
</div>

<h3 style="margin-top:1.4rem;opacity:0.85;">Funded</h3>
<div>
{% for grant in ext_funded %}
  {% include grant_entry.liquid %}
{% endfor %}
</div>

<h2 style="margin-top:2rem;">Internal funding (University of Glasgow &amp; Arizona State University)</h2>
<div>
{% for grant in int_funded %}
  {% include grant_entry.liquid %}
{% endfor %}
</div>

<script>
  (function () {
    function setFilter(role) {
      document.querySelectorAll('.grant').forEach(function (el) {
        el.style.display = role === 'all' || el.dataset.role === role ? '' : 'none';
      });
      document.querySelectorAll('.grant-filter-btn').forEach(function (b) {
        var active = b.dataset.role === role;
        b.classList.toggle('active', active);
        b.style.fontWeight = active ? '700' : '400';
        b.style.borderWidth = active ? '2px' : '1px';
      });
    }
    document.addEventListener('DOMContentLoaded', function () {
      document.querySelectorAll('.grant-filter-btn').forEach(function (b) {
        b.addEventListener('click', function () { setFilter(b.dataset.role); });
      });
    });
  })();
</script>
