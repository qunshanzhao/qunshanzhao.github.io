---
layout: page
permalink: /publications/
title: Publications
description: Publications from the University of Glasgow Enlighten repository — filter by type and year, or search. Linked author names are lab PhD students; badges mark papers where I am first or corresponding author.
nav: true
nav_order: 2
---

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div id="pub-filters" style="display:flex;flex-wrap:wrap;gap:8px;align-items:center;margin:14px 0 4px;">
  <button type="button" data-type="all" class="pub-type-btn" style="padding:0.3rem 0.8rem;border:1.5px solid currentColor;border-radius:1rem;background:none;font-weight:600;cursor:pointer;">All</button>
  <button type="button" data-type="journal" class="pub-type-btn" style="padding:0.3rem 0.8rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Journal articles</button>
  <button type="button" data-type="chapter" class="pub-type-btn" style="padding:0.3rem 0.8rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Book chapters</button>
  <button type="button" data-type="conf" class="pub-type-btn" style="padding:0.3rem 0.8rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">Conference &amp; other</button>
  <label style="margin-left:auto;">Year:
    <select id="pub-year-select" style="padding:0.25rem 0.5rem;border:1px solid currentColor;border-radius:0.4rem;background:none;color:inherit;">
      <option value="all">All</option>
    </select>
  </label>
</div>

<p style="font-size:0.86em;opacity:0.85;margin:6px 0 0;">
  Author names shown as links are members of the lab — <span style="color:#087f5b;font-weight:600;">green links</span> are PhD students I (co-)supervise(d), <a href="{{ '/people/' | relative_url }}">pink links</a> are other lab members (postdocs, research assistants, and visitors); click a name to jump to their profile.
  The <span style="display:inline-block;padding:0 7px;border:1px solid currentColor;border-radius:0.7rem;font-size:0.85em;font-weight:600;vertical-align:middle;">first author</span>
  and <span style="display:inline-block;padding:0 7px;border:1px solid currentColor;border-radius:0.7rem;font-size:0.85em;font-weight:600;vertical-align:middle;">corresponding author</span>
  badges mark my role on a paper, following my <a href="{{ '/assets/pdf/Qunshan_Zhao_CV.pdf' | relative_url }}">CV</a>.
</p>

<div class="publications pub-section" data-type="journal">

<h2 style="margin:1.4rem 0 0.2rem;">Journal articles</h2>

{% bibliography -q @article %}

</div>

<div class="publications pub-section" data-type="chapter">

<h2 style="margin:1.4rem 0 0.2rem;">Book chapters</h2>

{% bibliography -q @incollection %}

</div>

<div class="publications pub-section" data-type="conf">

<h2 style="margin:1.4rem 0 0.2rem;">Conference papers &amp; other</h2>

{% bibliography -q @inproceedings || @misc || @unpublished %}

</div>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    const buttons = document.querySelectorAll('.pub-type-btn');
    const sections = document.querySelectorAll('.pub-section');
    const yearSelect = document.getElementById('pub-year-select');

    // collect years from the bibliography year headings
    const years = new Set();
    document.querySelectorAll('.pub-section h2.bibliography').forEach(h => {
      const y = h.textContent.trim();
      if (/^\d{4}$/.test(y)) years.add(y);
    });
    Array.from(years).sort().reverse().forEach(y => {
      const o = document.createElement('option');
      o.value = y; o.textContent = y;
      yearSelect.appendChild(o);
    });

    function apply() {
      const type = document.querySelector('.pub-type-btn.active')?.dataset.type || 'all';
      const year = yearSelect.value;
      sections.forEach(sec => {
        const showSection = type === 'all' || sec.dataset.type === type;
        sec.style.display = showSection ? '' : 'none';
        if (!showSection) return;
        let currentYear = null;
        let sectionHasVisible = false;
        Array.from(sec.children).forEach(el => {
          if (el.matches('h2.bibliography') && /^\d{4}$/.test(el.textContent.trim())) {
            currentYear = el.textContent.trim();
            const show = year === 'all' || currentYear === year;
            el.style.display = show ? '' : 'none';
            if (show) sectionHasVisible = true;
          } else if (el.matches('ol.bibliography, ul.bibliography')) {
            const show = year === 'all' || currentYear === year;
            el.style.display = show ? '' : 'none';
          }
        });
        if (year !== 'all' && !sectionHasVisible) sec.style.display = 'none';
      });
      buttons.forEach(b => {
        const active = b.classList.contains('active');
        b.style.fontWeight = active ? '700' : '400';
        b.style.borderWidth = active ? '2px' : '1px';
      });
    }

    buttons.forEach(b => b.addEventListener('click', () => {
      buttons.forEach(x => x.classList.remove('active'));
      b.classList.add('active');
      apply();
    }));
    yearSelect.addEventListener('change', apply);
    buttons[0].classList.add('active');
    apply();
  });
</script>
