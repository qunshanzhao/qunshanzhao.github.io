---
layout: page
permalink: /blog/
title: Blog
nav: true
nav_order: 9
---

<div style="display:flex;gap:8px;margin:4px 0 18px;">
  <button type="button" id="tab-en" class="blog-tab" style="padding:0.35rem 1.1rem;border:2px solid currentColor;border-radius:1rem;background:none;font-weight:700;cursor:pointer;">English</button>
  <button type="button" id="tab-zh" class="blog-tab" style="padding:0.35rem 1.1rem;border:1px solid currentColor;border-radius:1rem;background:none;cursor:pointer;">中文</button>
</div>

{% assign en_posts = site.posts | where_exp: "p", "p.lang != 'zh'" %}
{% assign zh_posts = site.posts | where_exp: "p", "p.lang == 'zh'" %}

<div id="list-en">
{% for post in en_posts %}
  <div style="margin:0 0 26px;">
    <h3 style="margin:0 0 2px;"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p style="margin:0;font-size:0.85em;opacity:0.75;">{{ post.date | date: "%B %-d, %Y" }}</p>
    {% if post.description %}<p style="margin:4px 0 0;">{{ post.description }}</p>{% endif %}
  </div>
{% endfor %}
</div>

<div id="list-zh" style="display:none;">
{% for post in zh_posts %}
  <div style="margin:0 0 26px;">
    <h3 style="margin:0 0 2px;"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p style="margin:0;font-size:0.85em;opacity:0.75;">{{ post.date | date: "%Y 年 %-m 月 %-d 日" }}</p>
  </div>
{% endfor %}
</div>

<script>
  (function () {
    var en = document.getElementById('tab-en'), zh = document.getElementById('tab-zh');
    var listEn = document.getElementById('list-en'), listZh = document.getElementById('list-zh');
    function pick(which) {
      var isEn = which === 'en';
      listEn.style.display = isEn ? '' : 'none';
      listZh.style.display = isEn ? 'none' : '';
      en.style.fontWeight = isEn ? '700' : '400';
      en.style.borderWidth = isEn ? '2px' : '1px';
      zh.style.fontWeight = isEn ? '400' : '700';
      zh.style.borderWidth = isEn ? '1px' : '2px';
      if (history.replaceState) history.replaceState(null, '', isEn ? '#en' : '#zh');
    }
    en.addEventListener('click', function () { pick('en'); });
    zh.addEventListener('click', function () { pick('zh'); });
    if (location.hash === '#zh') pick('zh');
  })();
</script>
